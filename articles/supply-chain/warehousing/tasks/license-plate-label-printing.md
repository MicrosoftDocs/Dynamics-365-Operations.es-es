---
title: Habilitar la impresión de la etiqueta de matrícula
description: Este procedimiento le permite la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas.
author: perlynne
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8d906ca9f5a6536870fa0c322a0792ed5672c25e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558112"
---
# <a name="enable-license-plate-label-printing"></a><span data-ttu-id="d1a96-103">Habilitar la impresión de la etiqueta de matrícula</span><span class="sxs-lookup"><span data-stu-id="d1a96-103">Enable license plate label printing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d1a96-104">Este procedimiento le permite la impresión automática de una etiqueta de código de contenedor de envío en serie (SSCC) después de que el último artículo se selecciona del inventario en un proceso de trabajo de selección de ventas.</span><span class="sxs-lookup"><span data-stu-id="d1a96-104">This procedure enables the automatic printing of a Serial shipping container code (SSCC) label after the last item is picked from inventory in a sales picking work process.</span></span> <span data-ttu-id="d1a96-105">Puede ejecutar este procedimiento en la empresa USMF de los datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="d1a96-105">You can run this procedure in demo data company USMF.</span></span> <span data-ttu-id="d1a96-106">Si lo ejecuta mediante sus propios datos, debe tener una secuencia numérica configurada para las matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="d1a96-106">If you’re run it using your own data, you need to have a number sequence set up for license plates.</span></span> <span data-ttu-id="d1a96-107">Es necesario configurar una impresora de etiquetas para poder comenzar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="d1a96-107">You need to set up a label printer before you begin this task.</span></span> <span data-ttu-id="d1a96-108">Vaya a Administración de la organización > Configurar > Impresoras de red.</span><span class="sxs-lookup"><span data-stu-id="d1a96-108">Go to Organization administration > Setup > Network printers.</span></span> <span data-ttu-id="d1a96-109">En el panel de acciones, haga clic en Opciones y, a continuación, haga clic en el botón Descargar instalador del agente de ruta de documentos.</span><span class="sxs-lookup"><span data-stu-id="d1a96-109">On the Action pane, click Options, and then click the Download document routing agent installer button.</span></span> <span data-ttu-id="d1a96-110">Ejecute el instalador y asegúrese de que tiene una impresora de red de trabajo establecida en Activa para poder continuar con el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d1a96-110">Run the installer and make sure that you have a working network printer set to Active before you continue with the procedure.</span></span>


## <a name="set-up-the-gs1-company-prefix"></a><span data-ttu-id="d1a96-111">Configurar el prefijo GS1 de la empresa</span><span class="sxs-lookup"><span data-stu-id="d1a96-111">Set up the GS1 company prefix</span></span>
1. <span data-ttu-id="d1a96-112">Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="d1a96-112">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="d1a96-113">En el campo Prefijo GS1 de la empresa, escriba las 7 cifras del número GS1 de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d1a96-113">In the GS1 company prefix field, enter the 7 numbers for your GS1 company number.</span></span>
3. <span data-ttu-id="d1a96-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-114">Click Save.</span></span>
4. <span data-ttu-id="d1a96-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-115">Close the page.</span></span>

## <a name="setup-the-sscc-license-plate-number-sequence"></a><span data-ttu-id="d1a96-116">Configurar la secuencia de la matrícula de entidad de almacén de SSCC</span><span class="sxs-lookup"><span data-stu-id="d1a96-116">Setup the SSCC license plate number sequence</span></span>
1. <span data-ttu-id="d1a96-117">Vaya a Administración de la organización > Secuencias numéricas > Secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="d1a96-117">Go to Organization administration > Number sequences > Number sequences.</span></span>
2. <span data-ttu-id="d1a96-118">En el campo Área, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d1a96-118">In the Area field, select an option.</span></span>
3. <span data-ttu-id="d1a96-119">En el campo Referencia, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d1a96-119">In the Reference field, select an option.</span></span>
4. <span data-ttu-id="d1a96-120">En el campo Empresa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-120">In the Company field, type a value.</span></span>
5. <span data-ttu-id="d1a96-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d1a96-121">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="d1a96-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d1a96-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="d1a96-123">Expanda la sección Segmentos.</span><span class="sxs-lookup"><span data-stu-id="d1a96-123">Expand the Segments section.</span></span>
8. <span data-ttu-id="d1a96-124">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-124">Click Edit.</span></span>
9. <span data-ttu-id="d1a96-125">En la tabla de segmentos, seleccione la primera fila</span><span class="sxs-lookup"><span data-stu-id="d1a96-125">In the Segments table, select the first row</span></span>
10. <span data-ttu-id="d1a96-126">Haga clic en Quitar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-126">Click Remove.</span></span>
11. <span data-ttu-id="d1a96-127">Haga clic en Quitar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-127">Click Remove.</span></span>
12. <span data-ttu-id="d1a96-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-128">Click Save.</span></span>
13. <span data-ttu-id="d1a96-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-129">Close the page.</span></span>

## <a name="create-the-document-route-layout"></a><span data-ttu-id="d1a96-130">Crear el diseño de la ruta de documentos</span><span class="sxs-lookup"><span data-stu-id="d1a96-130">Create the document route layout</span></span>
1. <span data-ttu-id="d1a96-131">Vaya a Gestión de almacenes > Configurar > Ruta de documentos > Diseños de ruta de documentos.</span><span class="sxs-lookup"><span data-stu-id="d1a96-131">Go to Warehouse management > Setup > Document routing > Document routing layouts.</span></span>
    * <span data-ttu-id="d1a96-132">Habilite la configuración de SSCC.</span><span class="sxs-lookup"><span data-stu-id="d1a96-132">Enable the SSCC layout.</span></span>  
2. <span data-ttu-id="d1a96-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-133">Click New.</span></span>
3. <span data-ttu-id="d1a96-134">En el campo Id. de diseño, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-134">In the Layout ID field, type a value.</span></span>
4. <span data-ttu-id="d1a96-135">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-135">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d1a96-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d1a96-136">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="d1a96-137">Haga clic en Insertar al final del texto.</span><span class="sxs-lookup"><span data-stu-id="d1a96-137">Click Insert at end of text.</span></span>
7. <span data-ttu-id="d1a96-138">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-138">Click Save.</span></span>
8. <span data-ttu-id="d1a96-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-139">Close the page.</span></span>

## <a name="set-up-the-document-routing"></a><span data-ttu-id="d1a96-140">Configurar la ruta de documentos</span><span class="sxs-lookup"><span data-stu-id="d1a96-140">Set up the document routing</span></span>
1. <span data-ttu-id="d1a96-141">Vaya a Gestión de almacenes > Configurar > Ruta de documentos > Ruta de documentos.</span><span class="sxs-lookup"><span data-stu-id="d1a96-141">Go to Warehouse management > Setup > Document routing > Document routing.</span></span>
2. <span data-ttu-id="d1a96-142">En el campo Tipo de pedido de trabajo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d1a96-142">In the Work order type field, select an option.</span></span>
3. <span data-ttu-id="d1a96-143">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-143">Click New.</span></span>
4. <span data-ttu-id="d1a96-144">En el campo Almacén, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-144">In the Warehouse field, type a value.</span></span>
5. <span data-ttu-id="d1a96-145">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-145">In the Name field, type a value.</span></span>
6. <span data-ttu-id="d1a96-146">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-146">Click New.</span></span>
7. <span data-ttu-id="d1a96-147">En el campo Id. de diseño, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-147">In the Layout ID field, enter or select a value.</span></span>
8. <span data-ttu-id="d1a96-148">En el campo Nombre, especifique el nombre de la impresora que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-148">In the Name field, enter the printer name that you want to use..</span></span>
9. <span data-ttu-id="d1a96-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-149">Click Save.</span></span>
10. <span data-ttu-id="d1a96-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-150">Close the page.</span></span>

## <a name="create-mobile-device-menu"></a><span data-ttu-id="d1a96-151">Crear el menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="d1a96-151">Create mobile device menu</span></span>
1. <span data-ttu-id="d1a96-152">Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Elementos de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="d1a96-152">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="d1a96-153">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-153">Click New.</span></span>
3. <span data-ttu-id="d1a96-154">En el campo Nombre del elemento de menú, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-154">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="d1a96-155">En el campo Título, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-155">In the Title field, type a value.</span></span>
5. <span data-ttu-id="d1a96-156">En el campo Modo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d1a96-156">In the Mode field, select an option.</span></span>
6. <span data-ttu-id="d1a96-157">Seleccione Sí en el campo Usar trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="d1a96-157">Select Yes in the Use existing work field.</span></span>
7. <span data-ttu-id="d1a96-158">Seleccione Sí en el campo Generar matrícula de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="d1a96-158">Select Yes in the Generate license plate field.</span></span>
8. <span data-ttu-id="d1a96-159">Expanda la sección Clases de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-159">Expand the Work classes section.</span></span>
9. <span data-ttu-id="d1a96-160">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-160">Click New.</span></span>
10. <span data-ttu-id="d1a96-161">En el campo Identificador de la clase de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-161">In the Work class ID field, type a value.</span></span>
11. <span data-ttu-id="d1a96-162">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-162">Click Save.</span></span>
12. <span data-ttu-id="d1a96-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-163">Close the page.</span></span>
13. <span data-ttu-id="d1a96-164">Vaya a Gestión de almacenes > Configurar > Dispositivo móvil > Menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="d1a96-164">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
14. <span data-ttu-id="d1a96-165">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d1a96-165">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="d1a96-166">En el árbol, seleccione "En el árbol, seleccione el elemento de menú que ha creado antes".</span><span class="sxs-lookup"><span data-stu-id="d1a96-166">In the tree, select 'In the tree, select the menu item that you created before.'.</span></span>
16. <span data-ttu-id="d1a96-167">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-167">Click Edit.</span></span>
17. <span data-ttu-id="d1a96-168">Haga clic en la flecha para agregar el elemento de menú al menú.</span><span class="sxs-lookup"><span data-stu-id="d1a96-168">Click on the arrow to add the menu item to the menu.</span></span>
18. <span data-ttu-id="d1a96-169">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-169">Click Save.</span></span>
19. <span data-ttu-id="d1a96-170">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-170">Close the page.</span></span>

## <a name="update-a-work-template"></a><span data-ttu-id="d1a96-171">Actualizar una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="d1a96-171">Update a work template</span></span>
1. <span data-ttu-id="d1a96-172">Vaya a Gestión de almacenes > Configurar > Trabajo > Plantillas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-172">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="d1a96-173">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d1a96-173">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d1a96-174">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-174">Click Edit.</span></span>
4. <span data-ttu-id="d1a96-175">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d1a96-175">Click New.</span></span>
5. <span data-ttu-id="d1a96-176">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d1a96-176">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="d1a96-177">En el campo Tipo de trabajo, seleccione "Imprimir".</span><span class="sxs-lookup"><span data-stu-id="d1a96-177">In the Work type field, select 'Print'.</span></span>
7. <span data-ttu-id="d1a96-178">En el campo Identificador de la clase de trabajo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d1a96-178">In the Work class ID field, enter or select a value.</span></span>
8. <span data-ttu-id="d1a96-179">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d1a96-179">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d1a96-180">Haga clic en Subir.</span><span class="sxs-lookup"><span data-stu-id="d1a96-180">Click Move up.</span></span>
10. <span data-ttu-id="d1a96-181">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d1a96-181">Click Save.</span></span>
11. <span data-ttu-id="d1a96-182">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d1a96-182">Close the page.</span></span>

