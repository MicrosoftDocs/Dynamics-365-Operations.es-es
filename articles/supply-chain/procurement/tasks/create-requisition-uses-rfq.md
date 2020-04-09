---
title: Crear una solicitud que utilice una solicitud de presupuesto
description: Este tema explica cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqTableListPage, PurchReqCreate, PurchReqTable, PurchReqLineRelatedDocuments, EcoResCategorySingleLookup, PurchReqWorkflowDropDialog, WorkflowSubmitDialog, WorkflowStatus, WorkflowWorkItemActionDialog, WorkflowUserListLookup, PurchReqCopyRFQ, SysDataAreaSelectLookup, PurchRFQCaseTable, PurchRFQEditLines, PurchRFQReplyTable, UnitOfMeasureLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abe6745682030766eabcd4411121866c9d890be0
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149643"
---
# <a name="create-a-requisition-that-uses-an-rfq"></a><span data-ttu-id="5e1ff-103">Crear una solicitud que utilice una solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="5e1ff-103">Create a requisition that uses an RFQ</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5e1ff-104">Este tema explica cómo agregar la información del precio y del vendedor a una solicitud de compra desde un proceso de solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-104">This topic explains how to add price and vendor information to a purchase requisition from an RFQ process.</span></span> <span data-ttu-id="5e1ff-105">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF y debe haber iniciado sesión como administrador para completar todos los pasos.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-105">The example shown in this guide can be used in the USMF demo data company, and you must be logged in as an Admin to complete all the steps.</span></span> <span data-ttu-id="5e1ff-106">Las tareas de esta guía las realizarán normalmente profesionales de compras.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-106">The tasks in this guide would typically be done by procurement professionals.</span></span>


## <a name="create-a-requisition"></a><span data-ttu-id="5e1ff-107">Creación de una solicitud</span><span class="sxs-lookup"><span data-stu-id="5e1ff-107">Create a requisition</span></span>
1. <span data-ttu-id="5e1ff-108">En el Panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Solicitudes de compra > Solicitudes de compra preparadas por mí**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-108">In the navigation pane, go to **Modules > Procurement and sourcing > Purchase requisitions > Purchase requisitions prepared by me**.</span></span>
2. <span data-ttu-id="5e1ff-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-109">Select **New**.</span></span>
3. <span data-ttu-id="5e1ff-110">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-110">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="5e1ff-111">En el campo **Fecha solicitada**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-111">In the **Requested date** field, enter a date.</span></span>
5. <span data-ttu-id="5e1ff-112">En el campo **Fecha contable**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-112">In the **Accounting date** field, enter a date.</span></span>
6. <span data-ttu-id="5e1ff-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-113">Select **OK**.</span></span>
7. <span data-ttu-id="5e1ff-114">En el campo **Motivo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-114">In the **Reason** field, enter or select a value.</span></span>
8. <span data-ttu-id="5e1ff-115">Seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-115">Select **Add line**.</span></span>
9. <span data-ttu-id="5e1ff-116">En el campo **Categoría de compras**, seleccione una categoría en el árbol y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-116">In the **Procurement category** field, select a category in the tree, and then select **OK**.</span></span>
10. <span data-ttu-id="5e1ff-117">En el campo **Nombre de producto**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-117">In the **Product name** field, type a value.</span></span>
11. <span data-ttu-id="5e1ff-118">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-118">In the **Quantity** field, enter a number.</span></span>
12. <span data-ttu-id="5e1ff-119">En el campo **Unidad**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-119">In the **Unit** field, enter or select a value.</span></span>
13. <span data-ttu-id="5e1ff-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-120">Select **Save**.</span></span>
14. <span data-ttu-id="5e1ff-121">Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-121">Select **Workflow** to open the drop dialog.</span></span>
15. <span data-ttu-id="5e1ff-122">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-122">Select **Submit**.</span></span>
16. <span data-ttu-id="5e1ff-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-123">Close the page.</span></span>
17. <span data-ttu-id="5e1ff-124">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-124">Select **Submit**.</span></span>

## <a name="reassign-a-workflow-task"></a><span data-ttu-id="5e1ff-125">Reasignar una tarea de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5e1ff-125">Reassign a workflow task</span></span>
<span data-ttu-id="5e1ff-126">La siguiente tarea es crear una solicitud de presupuesto para obtener ofertas de proveedores para el producto.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-126">The next task is to create an RFQ to get bids from vendors for the product.</span></span> <span data-ttu-id="5e1ff-127">En los datos de demostración USMF, el flujo de trabajo de solicitud se configura para que, en el caso de que no se seleccione un proveedor, o el precio unitario sea 0 para una línea, se asigne una tarea a un trabajador específico para crear una solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-127">In USMF demo data, the requisition workflow is set up with a rule so that if a vendor is not selected, or the unit price is 0 for a line, a task is assigned to a specific worker to create an RFQ.</span></span> <span data-ttu-id="5e1ff-128">Para continuar con esta guía, necesita reasignar esa tarea a otro usuario (usted mismo).</span><span class="sxs-lookup"><span data-stu-id="5e1ff-128">To continue with this guide, you need to re-assign that task to another user (yourself).</span></span> <span data-ttu-id="5e1ff-129">Puede hacerlo solamente si inicia sesión como administrador.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-129">You can only do this if you are logged in as an Admin.</span></span>  

1. <span data-ttu-id="5e1ff-130">Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-130">Select **Workflow** to open the drop dialog.</span></span>
2. <span data-ttu-id="5e1ff-131">Seleccione **Ver el historial**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-131">Select **View history**.</span></span>
3. <span data-ttu-id="5e1ff-132">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-132">Refresh the page.</span></span>
4. <span data-ttu-id="5e1ff-133">Expanda la sección **Detalles de seguimiento**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-133">Expand the **Tracking details** section.</span></span>
5. <span data-ttu-id="5e1ff-134">En el árbol, seleccione la línea que empieza con "Activación del flujo de trabajo de elementos".</span><span class="sxs-lookup"><span data-stu-id="5e1ff-134">In the tree, select the line that starts with "Line workflow activated on".</span></span>
6. <span data-ttu-id="5e1ff-135">Seleccione **Ver detalles del flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-135">Select **View workflow details**.</span></span>
7. <span data-ttu-id="5e1ff-136">Expanda la sección **Elementos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-136">Expand the **Work items** section.</span></span>
8. <span data-ttu-id="5e1ff-137">Seleccione **Reasignar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-137">Select **Reassign**.</span></span>
9. <span data-ttu-id="5e1ff-138">En el campo **Usuario**, seleccione **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-138">In the **User** field, select **Admin**.</span></span>
10. <span data-ttu-id="5e1ff-139">Seleccione **Reasignar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-139">Select **Reassign**.</span></span>
11. <span data-ttu-id="5e1ff-140">Cierre las dos páginas.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-140">Close the two pages.</span></span>

## <a name="create-an-rfq"></a><span data-ttu-id="5e1ff-141">Crear una solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="5e1ff-141">Create an RFQ</span></span>

1. <span data-ttu-id="5e1ff-142">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-142">Refresh the page.</span></span>
2. <span data-ttu-id="5e1ff-143">Seleccione **Solicitud de presupuesto**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-143">Select **Request for quotation**.</span></span>
3. <span data-ttu-id="5e1ff-144">En el campo **Entidad jurídica compradora**, seleccione **USMF**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-144">In the **Buying legal entity** field, select **USMF**.</span></span> <span data-ttu-id="5e1ff-145">Debe seleccionar la misma entidad jurídica que se encuentra en la línea de solicitud.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-145">You must select the same legal entity that's on the requisition line.</span></span>  
4. <span data-ttu-id="5e1ff-146">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-146">In the list, mark the selected row.</span></span> <span data-ttu-id="5e1ff-147">Si tenía varias líneas en su solicitud de compra, seleccione todas las líneas que usted quiere agregar a la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-147">If you had multiple lines on your purchase requisition, select all the lines that you want to add to the RFQ.</span></span>  
5. <span data-ttu-id="5e1ff-148">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-148">Select **OK**.</span></span>
6. <span data-ttu-id="5e1ff-149">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-149">Refresh the page.</span></span>
7. <span data-ttu-id="5e1ff-150">Asegúrese de que la ficha desplegable está abierta y, después, expanda la sección **Documentos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-150">Ensure that the FactBox is open, then expand the **Related documents** section.</span></span>
8. <span data-ttu-id="5e1ff-151">Seleccione el vínculo en el campo **Solicitud de presupuesto** para abrir la solicitud de presupuesto que se acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-151">Select the link in the **Request for quotation** field to open the RFQ that was just created.</span></span>
9. <span data-ttu-id="5e1ff-152">Seleccione **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-152">Select **Header**.</span></span>
10. <span data-ttu-id="5e1ff-153">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-153">Select **Add**.</span></span>
11. <span data-ttu-id="5e1ff-154">En el campo **Cuenta de proveedor**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-154">In the **Vendor account** field, enter or select a value.</span></span>
12. <span data-ttu-id="5e1ff-155">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-155">Select **Add**.</span></span>
13. <span data-ttu-id="5e1ff-156">En el campo **Cuenta de proveedor**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-156">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="5e1ff-157">Seleccione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-157">Select **Send**.</span></span>
15. <span data-ttu-id="5e1ff-158">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-158">Select **OK**.</span></span>
16. <span data-ttu-id="5e1ff-159">Seleccione **Especificar respuesta**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-159">Select **Enter reply**.</span></span>
17. <span data-ttu-id="5e1ff-160">En el panel de acciones, haga clic en **Responder**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-160">On the Action Pane, select **Reply**.</span></span>
18. <span data-ttu-id="5e1ff-161">Seleccione **Copiar datos a respuesta**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-161">Select **Copy data to reply**.</span></span> <span data-ttu-id="5e1ff-162">Esto copia datos, como la cantidad y las fechas, de la solicitud de presupuesto a la respuesta.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-162">This copies data, such as the quantity and dates, from the RFQ to the reply.</span></span>  
19. <span data-ttu-id="5e1ff-163">En el campo **Precio unitario**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-163">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="5e1ff-164">Este es el precio que ha recibido del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-164">This is the price that you've received from the vendor.</span></span> <span data-ttu-id="5e1ff-165">También es posible que desee especificar información adicional del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-165">You might also want to enter additional information from the vendor.</span></span>  
20. <span data-ttu-id="5e1ff-166">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-166">Select **Accept**.</span></span>
21. <span data-ttu-id="5e1ff-167">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-167">Select **OK**.</span></span>

## <a name="verify-that-vendor-and-price-have-been-transferred-to-the-requisition"></a><span data-ttu-id="5e1ff-168">Comprobar que el proveedor y el precio se han transferido a la solicitud</span><span class="sxs-lookup"><span data-stu-id="5e1ff-168">Verify that vendor and price have been transferred to the requisition</span></span>
1. <span data-ttu-id="5e1ff-169">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-169">Close the page.</span></span>
2. <span data-ttu-id="5e1ff-170">Seleccionar **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-170">Select **Lines**.</span></span>
3. <span data-ttu-id="5e1ff-171">Seleccione **Información relacionada**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-171">Select **Related information**.</span></span>
4. <span data-ttu-id="5e1ff-172">Seleccionar **Solicitud de compra**.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-172">Select **Purchase requisition**.</span></span>
5. <span data-ttu-id="5e1ff-173">Seleccione la línea que se transfirió a la solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-173">Select the line that was transferred to the RFQ.</span></span> <span data-ttu-id="5e1ff-174">Compruebe que el precio y el proveedor se han copiado a la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-174">Verify that the price and vendor have been copied to the requisition.</span></span>  
6. <span data-ttu-id="5e1ff-175">Seleccione **Flujo de trabajo** para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-175">Select **Workflow** to open the drop dialog.</span></span>
7. <span data-ttu-id="5e1ff-176">Seleccione Completar.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-176">Select Complete.</span></span>
8. <span data-ttu-id="5e1ff-177">Seleccionar la página.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-177">Select the page.</span></span>
9. <span data-ttu-id="5e1ff-178">Seleccione Completar.</span><span class="sxs-lookup"><span data-stu-id="5e1ff-178">Select Complete.</span></span>

