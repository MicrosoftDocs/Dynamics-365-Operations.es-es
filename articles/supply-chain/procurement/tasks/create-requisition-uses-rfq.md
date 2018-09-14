--- 
title: Crear una solicitud que utilice una solicitud de presupuesto
description: "En esta guía se muestra cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra."
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 8a9418b526f992008086f10ce78e95cb682bc164
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="8eba1-103">Crear una solicitud que utilice una solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="8eba1-103">Create a requisition that uses an RFQ</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8eba1-104">En esta guía se muestra cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="8eba1-104">This guide shows how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="8eba1-105">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF y debe haber iniciado sesión como administrador para completar todos los pasos.</span><span class="sxs-lookup"><span data-stu-id="8eba1-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="8eba1-106">Las tareas de esta guía las realizarán normalmente profesionales de compras.</span><span class="sxs-lookup"><span data-stu-id="8eba1-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="8eba1-107">Creación de una solicitud</span><span class="sxs-lookup"><span data-stu-id="8eba1-107">Create a requisition</span></span>
1. <span data-ttu-id="8eba1-108">Vaya a Adquisición y abastecimiento > Solicitudes de compra > Solicitudes de compra preparadas por mí.</span><span class="sxs-lookup"><span data-stu-id="8eba1-108">Go to Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me.</span></span>
2. <span data-ttu-id="8eba1-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-109">Click New.</span></span>
3. <span data-ttu-id="8eba1-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="8eba1-111">En el campo Fecha solicitada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="8eba1-111">In the Requested date field, enter a date.</span></span>
5. <span data-ttu-id="8eba1-112">En el campo Fecha contable, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="8eba1-112">In the Accounting date field, enter a date.</span></span>
6. <span data-ttu-id="8eba1-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8eba1-113">Click OK.</span></span>
7. <span data-ttu-id="8eba1-114">En el campo Motivo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-114">In the Reason field, enter or select a value.</span></span>
8. <span data-ttu-id="8eba1-115">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="8eba1-115">Click Add line.</span></span>
9. <span data-ttu-id="8eba1-116">En el campo Categoría de compras , seleccione una categoría en el árbol y, a continuación, haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-116">In the Procurement category field, select a category in the tree, and then click OK.</span></span>
10. <span data-ttu-id="8eba1-117">En el campo Nombre de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-117">In the Product name field, type a value.</span></span>
11. <span data-ttu-id="8eba1-118">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8eba1-118">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="8eba1-119">En el campo Unidad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-119">In the Unit field, enter or select a value.</span></span>
13. <span data-ttu-id="8eba1-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-120">Click Save.</span></span>
14. <span data-ttu-id="8eba1-121">Haga clic en Flujo de trabajo para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-121">Click Workflow to open the drop dialog.</span></span>
15. <span data-ttu-id="8eba1-122">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-122">Click Submit.</span></span>
16. <span data-ttu-id="8eba1-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-123">Close the page.</span></span>
17. <span data-ttu-id="8eba1-124">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-124">Click Submit.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="8eba1-125">Reasignar una tarea de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="8eba1-125">Reassign a workflow task</span></span>
    * <span data-ttu-id="8eba1-126">La siguiente tarea es crear una solicitud de presupuesto para obtener ofertas de proveedores para el producto.</span><span class="sxs-lookup"><span data-stu-id="8eba1-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="8eba1-127">En los datos de demostración USMF, el flujo de trabajo de solicitud se configura para que, en el caso de que no se seleccione un proveedor, o el precio unitario sea 0 para una línea, se asigne una tarea a un trabajador específico para crear una solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="8eba1-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="8eba1-128">Para continuar con esta guía, necesita reasignar esa tarea a otro usuario (usted mismo).</span><span class="sxs-lookup"><span data-stu-id="8eba1-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="8eba1-129">Puede hacerlo solamente si inicia sesión como administrador.</span><span class="sxs-lookup"><span data-stu-id="8eba1-129">You can only do this if you are logged in as an Admin.</span></span>  
1. <span data-ttu-id="8eba1-130">Haga clic en Flujo de trabajo para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-130">Click Workflow to open the drop dialog.</span></span>
2. <span data-ttu-id="8eba1-131">Haga clic en Ver historial.</span><span class="sxs-lookup"><span data-stu-id="8eba1-131">Click View history.</span></span>
3. <span data-ttu-id="8eba1-132">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-132">Refresh the page.</span></span>
4. <span data-ttu-id="8eba1-133">Expanda la sección Detalles de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8eba1-133">Expand the Tracking details section.</span></span>
5. <span data-ttu-id="8eba1-134">En el árbol, seleccione “la línea que empieza con “Activación del flujo de trabajo de elementos””.</span><span class="sxs-lookup"><span data-stu-id="8eba1-134">In the tree, select 'the line that starts with “Line workflow activated on”'.</span></span>
6. <span data-ttu-id="8eba1-135">Haga clic en Ver detalles del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-135">Click View workflow details.</span></span>
7. <span data-ttu-id="8eba1-136">Expanda la sección Elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-136">Expand the Work items section.</span></span>
8. <span data-ttu-id="8eba1-137">Haga clic en Reasignar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-137">Click Reassign.</span></span>
9. <span data-ttu-id="8eba1-138">En el campo Usuario, seleccione Administrador.</span><span class="sxs-lookup"><span data-stu-id="8eba1-138">In the User field, select Admin.</span></span>
10. <span data-ttu-id="8eba1-139">Haga clic en Reasignar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-139">Click Reassign.</span></span>
11. <span data-ttu-id="8eba1-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-140">Close the page.</span></span>
12. <span data-ttu-id="8eba1-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-141">Close the page.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="8eba1-142">Crear una solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="8eba1-142">Create an RFQ</span></span>
1. <span data-ttu-id="8eba1-143">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-143">Refresh the page.</span></span>
2. <span data-ttu-id="8eba1-144">Haga clic en Solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="8eba1-144">Click Request for quotation.</span></span>
3. <span data-ttu-id="8eba1-145">En el campo Entidad jurídica compradora, seleccione USMF.</span><span class="sxs-lookup"><span data-stu-id="8eba1-145">In the Buying legal entity field, select USMF.</span></span>
    * <span data-ttu-id="8eba1-146">Debe seleccionar la misma entidad jurídica que se encuentra en la línea de solicitud.</span><span class="sxs-lookup"><span data-stu-id="8eba1-146">You must select the same legal entity that’s on the requisition line.</span></span>  
4. <span data-ttu-id="8eba1-147">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8eba1-147">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8eba1-148">Si tenía varias líneas en su solicitud de compra, seleccione todas las líneas que usted quiere agregar a la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="8eba1-148">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="8eba1-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8eba1-149">Click OK.</span></span>
6. <span data-ttu-id="8eba1-150">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-150">Refresh the page.</span></span>
7. <span data-ttu-id="8eba1-151">Abra el cuadro informativo y, a continuación, expanda la sección Documentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="8eba1-151">Open the FactBox and then expand the Related documents section.</span></span>
    * <span data-ttu-id="8eba1-152">Puede tener ya el cuadro informativo abierto.</span><span class="sxs-lookup"><span data-stu-id="8eba1-152">You may already have the FactBox open.</span></span> <span data-ttu-id="8eba1-153">Busque el icono con una flecha encima, a la derecha de los botones de alternancia Línea/Encabezado.</span><span class="sxs-lookup"><span data-stu-id="8eba1-153">Look for the icon with an arrow on it, to the right of the Lines/Header toggle buttons.</span></span> <span data-ttu-id="8eba1-154">Si la flecha está señalando a la derecha, el cuadro informativo ya está abierto.</span><span class="sxs-lookup"><span data-stu-id="8eba1-154">If the arrow is pointing to the right, the FactBox is already open.</span></span> <span data-ttu-id="8eba1-155">Si la flecha señala a la izquierda, haga clic en ella para abrir el cuadro informativo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-155">If the arrow points to the left, click it to open the FactBox.</span></span>  
8. <span data-ttu-id="8eba1-156">Haga clic en el vínculo en el campo Solicitud de presupuesto para abrir la solicitud de presupuesto que se acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="8eba1-156">Click the link in the Request for quotation field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="8eba1-157">Haga clic en Encabezado.</span><span class="sxs-lookup"><span data-stu-id="8eba1-157">Click Header.</span></span>
10. <span data-ttu-id="8eba1-158">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-158">Click Add.</span></span>
11. <span data-ttu-id="8eba1-159">En el campo Cuenta de proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-159">In the Vendor account field, enter or select a value.</span></span>
12. <span data-ttu-id="8eba1-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-160">Click Add.</span></span>
13. <span data-ttu-id="8eba1-161">En el campo Cuenta de proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-161">In the Vendor account field, enter or select a value.</span></span>
14. <span data-ttu-id="8eba1-162">Haga clic en Enviar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-162">Click Send.</span></span>
15. <span data-ttu-id="8eba1-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8eba1-163">Click OK.</span></span>
16. <span data-ttu-id="8eba1-164">Haga clic en Especificar respuesta.</span><span class="sxs-lookup"><span data-stu-id="8eba1-164">Click Enter reply.</span></span>
17. <span data-ttu-id="8eba1-165">En el panel de acciones, haga clic en Contestación.</span><span class="sxs-lookup"><span data-stu-id="8eba1-165">On the Action Pane, click Reply.</span></span>
18. <span data-ttu-id="8eba1-166">Haga clic en Copiar datos en respuesta.</span><span class="sxs-lookup"><span data-stu-id="8eba1-166">Click Copy data to reply.</span></span>
    * <span data-ttu-id="8eba1-167">Esto copia datos, como la cantidad y las fechas, de la solicitud de presupuesto a la respuesta.</span><span class="sxs-lookup"><span data-stu-id="8eba1-167">This copies data, such as the quantity and dates, from the RFQ to the reply .</span></span>  
19. <span data-ttu-id="8eba1-168">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="8eba1-168">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="8eba1-169">Este es el precio que ha recibido del proveedor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-169">This is the price that you’ve received from the vendor.</span></span> <span data-ttu-id="8eba1-170">También es posible que desee especificar información adicional del proveedor.</span><span class="sxs-lookup"><span data-stu-id="8eba1-170">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="8eba1-171">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-171">Click Accept.</span></span>
21. <span data-ttu-id="8eba1-172">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8eba1-172">Click OK.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="8eba1-173">Comprobar que el proveedor y el precio se han transferido a la solicitud</span><span class="sxs-lookup"><span data-stu-id="8eba1-173">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="8eba1-174">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-174">Close the page.</span></span>
2. <span data-ttu-id="8eba1-175">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="8eba1-175">Click Lines.</span></span>
3. <span data-ttu-id="8eba1-176">Haga clic en Información relacionada.</span><span class="sxs-lookup"><span data-stu-id="8eba1-176">Click Related information.</span></span>
4. <span data-ttu-id="8eba1-177">Haga clic en Solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="8eba1-177">Click Purchase requisition.</span></span>
5. <span data-ttu-id="8eba1-178">Seleccione la línea que se transfirió a la solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="8eba1-178">Select the line that was transferred to the RFQ.</span></span>
    * <span data-ttu-id="8eba1-179">Compruebe que el precio y el proveedor se han copiado a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="8eba1-179">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="8eba1-180">Haga clic en Flujo de trabajo para abrir el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8eba1-180">Click Workflow to open the drop dialog.</span></span>
7. <span data-ttu-id="8eba1-181">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-181">Click Complete.</span></span>
8. <span data-ttu-id="8eba1-182">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8eba1-182">Close the page.</span></span>
9. <span data-ttu-id="8eba1-183">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="8eba1-183">Click Complete.</span></span>


