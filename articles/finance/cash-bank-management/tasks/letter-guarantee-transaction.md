---
title: Transacción de carta de garantía
description: Este procedimiento le muestra el proceso de Carta de garantía.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff105bdefff2ea93c853d590c77391653f50a4dc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179799"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="a2458-103">Transacción de carta de garantía</span><span class="sxs-lookup"><span data-stu-id="a2458-103">Letter of guarantee transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a2458-104">Este procedimiento le muestra el proceso de Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="a2458-105">Las siguientes tareas se deben realizar antes de completar este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="a2458-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="a2458-106">Configuración de servicios bancarios y perfiles para una carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="a2458-107">Creación de un contrato de servicios bancarios para una carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="a2458-108">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="a2458-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="a2458-109">Crear pedido de ventas con carta de garantía</span><span class="sxs-lookup"><span data-stu-id="a2458-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="a2458-110">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="a2458-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a2458-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a2458-111">Click New.</span></span>
3. <span data-ttu-id="a2458-112">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="a2458-113">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="a2458-113">Expand the General section.</span></span>
5. <span data-ttu-id="a2458-114">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="a2458-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a2458-116">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="a2458-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="a2458-118">En el campo Tipo de documento bancario, seleccione "Carta de garantía".</span><span class="sxs-lookup"><span data-stu-id="a2458-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="a2458-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-119">Click OK.</span></span>
11. <span data-ttu-id="a2458-120">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="a2458-121">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2458-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="a2458-122">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="a2458-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="a2458-123">Haga clic en la pestaña Entrega.</span><span class="sxs-lookup"><span data-stu-id="a2458-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="a2458-124">Nota: Seleccione Control de fecha de entrega = Ninguno</span><span class="sxs-lookup"><span data-stu-id="a2458-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="a2458-125">En el campo Fecha de envío solicitada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="a2458-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="a2458-126">En el campo Fecha de envío confirmada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="a2458-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="a2458-127">Procesar carta de garantía_Solicitar</span><span class="sxs-lookup"><span data-stu-id="a2458-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="a2458-128">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="a2458-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="a2458-129">Haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="a2458-130">En el Panel de acciones, haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="a2458-131">Haga clic en Solicitud para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="a2458-132">En el campo Tipo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="a2458-133">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="a2458-134">En el campo Valor, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a2458-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="a2458-135">En el campo Fecha de vencimiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="a2458-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="a2458-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-136">Click OK.</span></span>
10. <span data-ttu-id="a2458-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2458-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="a2458-138">Procesar carta de garantía_Enviar al banco</span><span class="sxs-lookup"><span data-stu-id="a2458-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="a2458-139">Vaya a Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="a2458-140">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2458-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a2458-141">Haga clic en Enviar al banco para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="a2458-142">En el campo Cuenta bancaria, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="a2458-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a2458-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="a2458-145">Procesar carta de garantía_Recibir del banco</span><span class="sxs-lookup"><span data-stu-id="a2458-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="a2458-146">Haga clic en Recibir del banco para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="a2458-147">En el campo Número del banco, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2458-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="a2458-148">Compruebe los valores en los campos Margen y Gasto calculados.</span><span class="sxs-lookup"><span data-stu-id="a2458-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="a2458-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-149">Click OK.</span></span>
4. <span data-ttu-id="a2458-150">Expanda la sección Acciones.</span><span class="sxs-lookup"><span data-stu-id="a2458-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="a2458-151">Compruebe el registro "Recibir del banco".</span><span class="sxs-lookup"><span data-stu-id="a2458-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="a2458-152">Haga clic para seguir el vínculo en el campo Número de lote de diario.</span><span class="sxs-lookup"><span data-stu-id="a2458-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="a2458-153">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="a2458-153">Click Lines.</span></span>
    * <span data-ttu-id="a2458-154">Compruebe el registro de entradas del diario.</span><span class="sxs-lookup"><span data-stu-id="a2458-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="a2458-155">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2458-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="a2458-156">Procesar carta de garantía_Entregar a beneficiario</span><span class="sxs-lookup"><span data-stu-id="a2458-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="a2458-157">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="a2458-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a2458-158">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="a2458-159">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="a2458-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="a2458-160">Haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="a2458-161">En el Panel de acciones, haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="a2458-162">Haga clic en Entregar a beneficiario para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="a2458-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-163">Click OK.</span></span>
8. <span data-ttu-id="a2458-164">Vaya a Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="a2458-165">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2458-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a2458-166">Haga clic en Entregar a beneficiario para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="a2458-167">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-167">Click OK.</span></span>
12. <span data-ttu-id="a2458-168">Expanda la sección Acciones.</span><span class="sxs-lookup"><span data-stu-id="a2458-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="a2458-169">Valide el registro "Entregar a beneficiario".</span><span class="sxs-lookup"><span data-stu-id="a2458-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="a2458-170">Procesar carta de garantía_Aumentar valor</span><span class="sxs-lookup"><span data-stu-id="a2458-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="a2458-171">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="a2458-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a2458-172">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="a2458-173">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="a2458-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="a2458-174">Haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="a2458-175">En el Panel de acciones, haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="a2458-176">Haga clic en Aumentar valor para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="a2458-177">En el campo Valor para agregar, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a2458-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="a2458-178">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-178">Click OK.</span></span>
9. <span data-ttu-id="a2458-179">Vaya a Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="a2458-180">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2458-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="a2458-181">Haga clic en Aumentar valor para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="a2458-182">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-182">Click OK.</span></span>
13. <span data-ttu-id="a2458-183">Expanda la sección Acciones.</span><span class="sxs-lookup"><span data-stu-id="a2458-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="a2458-184">Compruebe el registro "Aumentar valor".</span><span class="sxs-lookup"><span data-stu-id="a2458-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="a2458-185">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2458-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="a2458-186">Haga clic para seguir el vínculo en el campo Número de lote de diario.</span><span class="sxs-lookup"><span data-stu-id="a2458-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="a2458-187">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="a2458-187">Click Lines.</span></span>
    * <span data-ttu-id="a2458-188">Compruebe las entradas del diario registradas.</span><span class="sxs-lookup"><span data-stu-id="a2458-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="a2458-189">Procesar carta de garantía_Liquidar</span><span class="sxs-lookup"><span data-stu-id="a2458-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="a2458-190">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="a2458-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="a2458-191">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2458-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="a2458-192">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="a2458-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="a2458-193">Haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="a2458-194">En el Panel de acciones, haga clic en Carta de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="a2458-195">Haga clic en Liquidar para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="a2458-196">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-196">Click OK.</span></span>
8. <span data-ttu-id="a2458-197">Vaya a Gestión de efectivo y bancos > Cartas de garantía > Cartas de garantía.</span><span class="sxs-lookup"><span data-stu-id="a2458-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="a2458-198">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2458-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="a2458-199">Haga clic en Liquidar para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="a2458-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="a2458-200">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a2458-200">Click OK.</span></span>
12. <span data-ttu-id="a2458-201">Expanda la sección Acciones.</span><span class="sxs-lookup"><span data-stu-id="a2458-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="a2458-202">Compruebe el registro "Liquidar".</span><span class="sxs-lookup"><span data-stu-id="a2458-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="a2458-203">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2458-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="a2458-204">Haga clic para seguir el vínculo en el campo Número de lote de diario.</span><span class="sxs-lookup"><span data-stu-id="a2458-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="a2458-205">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="a2458-205">Click Lines.</span></span>
    * <span data-ttu-id="a2458-206">Compruebe las entradas del diario registradas.</span><span class="sxs-lookup"><span data-stu-id="a2458-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="a2458-207">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2458-207">Close the page.</span></span>

