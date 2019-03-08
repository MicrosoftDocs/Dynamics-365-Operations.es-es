---
title: Importar créditos documentarios
description: Este procedimiento le muestra el proceso para importar una carta de crédito.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts, PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, BankLCImport,  PurchEditLines, VendEditInvoice, SrsReportViewerForm, LedgerJournalTable, LedgerJournalTransVendPaym, VendOpenTrans, SysQueryForm, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1768494182a79d7a33044498c1e768e61d937d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "313575"
---
# <a name="import-letter-of-credit"></a><span data-ttu-id="d7eb9-103">Importar créditos documentarios</span><span class="sxs-lookup"><span data-stu-id="d7eb9-103">Import letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d7eb9-104">Este procedimiento le muestra el proceso para importar una carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="d7eb9-105">Se debe configurar lo siguiente para completar este procedimiento: instalaciones bancarias, perfiles de contabilización, un acuerdo de instalaciones bancarias e información bancaria del proveedor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="d7eb9-106">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="d7eb9-107">Crear un pedido de compra con carta de crédito</span><span class="sxs-lookup"><span data-stu-id="d7eb9-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="d7eb9-108">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="d7eb9-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-109">Click New.</span></span>
3. <span data-ttu-id="d7eb9-110">En el campo Cuenta de proveedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="d7eb9-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d7eb9-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d7eb9-113">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-113">Expand the General section.</span></span>
7. <span data-ttu-id="d7eb9-114">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="d7eb9-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d7eb9-116">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="d7eb9-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="d7eb9-118">En el campo Fecha contable, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="d7eb9-119">En el campo Fecha de entrega, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="d7eb9-120">Nota: Se debe seleccionar el campo "Tipo de documento bancario" con el valor "Crédito documentario".</span><span class="sxs-lookup"><span data-stu-id="d7eb9-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="d7eb9-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d7eb9-121">Click OK.</span></span>
14. <span data-ttu-id="d7eb9-122">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="d7eb9-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d7eb9-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d7eb9-125">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="d7eb9-126">Haga clic en la ficha Entrega.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="d7eb9-127">En el campo Fecha de entrega, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="d7eb9-128">En el campo Fecha de entrega confirmada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="d7eb9-129">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="d7eb9-130">Defina los detalles de la carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="d7eb9-131">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="d7eb9-132">Haga clic en Crédito documentario/remesa documentaria.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="d7eb9-133">En el campo Fecha de solicitud, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="d7eb9-134">Compruebe que el campo "Cuenta bancaria" tiene la cuenta bancaria activa predeterminada, que se basa en la fecha de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="d7eb9-135">En el campo Número de documento bancario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="d7eb9-136">En el campo Fecha de recepción, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="d7eb9-137">Expanda la sección Documento bancario.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="d7eb9-138">En el campo Fecha de vencimiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="d7eb9-139">Expanda la sección Detalles del banco.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="d7eb9-140">En el campo Banco avisador, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="d7eb9-141">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="d7eb9-142">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-142">Click Save.</span></span>
33. <span data-ttu-id="d7eb9-143">Haga clic en Obtener envíos de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="d7eb9-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-144">Close the page.</span></span>
35. <span data-ttu-id="d7eb9-145">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="d7eb9-146">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-146">Click Confirm.</span></span>
37. <span data-ttu-id="d7eb9-147">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="d7eb9-148">Haga clic en Crédito documentario/remesa documentaria.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="d7eb9-149">Haga clic Procesar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-149">Click Process.</span></span>
40. <span data-ttu-id="d7eb9-150">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-150">Click Confirm.</span></span>
    * <span data-ttu-id="d7eb9-151">Compruebe que el saldo del crédito reduce el importe del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="d7eb9-152">En este ejemplo, Importe de compra = 500,00, Límite de crédito = 10000,00, por lo tanto, Saldo del crédito = 9500,00.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="d7eb9-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-153">Close the page.</span></span>
42. <span data-ttu-id="d7eb9-154">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="d7eb9-155">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-155">Click Save.</span></span>
44. <span data-ttu-id="d7eb9-156">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="d7eb9-157">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-157">Click Confirm.</span></span>
    * <span data-ttu-id="d7eb9-158">Modifique la carta de crédito, debido al cambio del precio por unidad.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="d7eb9-159">En el panel de acciones, haga clic en Gestionar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="d7eb9-160">Haga clic en Crédito documentario/remesa documentaria.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="d7eb9-161">Modifique la carta de crédito, debido al cambio del Precio unitario de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="d7eb9-162">Haga clic Procesar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-162">Click Process.</span></span>
49. <span data-ttu-id="d7eb9-163">Haga Clic en Enmendar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-163">Click Amend.</span></span>
50. <span data-ttu-id="d7eb9-164">Haga clic en Quitar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-164">Click Remove.</span></span>
51. <span data-ttu-id="d7eb9-165">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-165">Click Yes.</span></span>
52. <span data-ttu-id="d7eb9-166">Haga clic en Obtener envíos de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="d7eb9-167">Haga clic Procesar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-167">Click Process.</span></span>
54. <span data-ttu-id="d7eb9-168">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-168">Click Confirm.</span></span>
    * <span data-ttu-id="d7eb9-169">Compruebe que el saldo del crédito reduce el importe del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="d7eb9-170">En este ejemplo, Importe de compra editado= 600,00, Límite de crédito = 10000,00, por lo tanto, Saldo del crédito = 9400,00.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="d7eb9-171">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="d7eb9-172">Registrar albarán</span><span class="sxs-lookup"><span data-stu-id="d7eb9-172">Post Packing slip</span></span>
1. <span data-ttu-id="d7eb9-173">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="d7eb9-174">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-174">Click Product receipt.</span></span>
3. <span data-ttu-id="d7eb9-175">En el campo PurchParmTable_Num, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="d7eb9-176">Seleccione el Número de envío creado con referencia a la carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="d7eb9-177">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d7eb9-178">En el campo Fecha de recepción de producto, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="d7eb9-179">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d7eb9-179">Click OK.</span></span>
7. <span data-ttu-id="d7eb9-180">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-180">Close the page.</span></span>
8. <span data-ttu-id="d7eb9-181">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="d7eb9-182">Compruebe el estado de la carta de crédito de importación.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="d7eb9-183">Vaya a Gestión de efectivo y bancos > Carta de crédito > Importar carta de crédito e importar cobro.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="d7eb9-184">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d7eb9-185">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d7eb9-186">Compruebe el estado de la carta de crédito de importación.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-186">Verify the Import letter of credit status.</span></span>    
    *   
4. <span data-ttu-id="d7eb9-187">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-187">Close the page.</span></span>
5. <span data-ttu-id="d7eb9-188">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="d7eb9-189">Registrar factura de compra</span><span class="sxs-lookup"><span data-stu-id="d7eb9-189">Post purchase invoice</span></span>
1. <span data-ttu-id="d7eb9-190">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="d7eb9-191">Seleccione el pedido de compra creado con la carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="d7eb9-192">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d7eb9-193">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d7eb9-194">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="d7eb9-195">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-195">Click Invoice.</span></span>
6. <span data-ttu-id="d7eb9-196">En el campo Número, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="d7eb9-197">En el campo Número de envío, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="d7eb9-198">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d7eb9-199">En el campo Fecha de la factura, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="d7eb9-200">Haga clic en Actualizar estado de conciliación.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-200">Click Update match status.</span></span>
11. <span data-ttu-id="d7eb9-201">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-201">Click Post.</span></span>
12. <span data-ttu-id="d7eb9-202">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-202">Close the page.</span></span>
13. <span data-ttu-id="d7eb9-203">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="d7eb9-204">Compruebe el estado de la carta de crédito de importación.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="d7eb9-205">Vaya a Gestión de efectivo y bancos > Carta de crédito > Importar carta de crédito e importar cobro.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="d7eb9-206">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d7eb9-207">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d7eb9-208">Compruebe la carta de crédito de importación.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="d7eb9-209">Validar: Estado de envío = detalles de créditos bancarios facturados</span><span class="sxs-lookup"><span data-stu-id="d7eb9-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="d7eb9-210">Haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-210">Click View.</span></span>
5. <span data-ttu-id="d7eb9-211">Haga clic en Imprimir solicitud.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-211">Click Print application.</span></span>
6. <span data-ttu-id="d7eb9-212">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d7eb9-212">Click OK.</span></span>
    * <span data-ttu-id="d7eb9-213">Compruebe que se imprime la solicitud de la carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="d7eb9-214">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-214">Close the page.</span></span>
8. <span data-ttu-id="d7eb9-215">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-215">Close the page.</span></span>
9. <span data-ttu-id="d7eb9-216">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="d7eb9-217">Registre el diario de pagos del proveedor para la factura de compra creada con la carta de crédito</span><span class="sxs-lookup"><span data-stu-id="d7eb9-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="d7eb9-218">Vaya a Proveedores > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="d7eb9-219">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-219">Click New.</span></span>
3. <span data-ttu-id="d7eb9-220">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="d7eb9-221">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="d7eb9-222">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-222">Click Lines.</span></span>
6. <span data-ttu-id="d7eb9-223">En el campo Fecha, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="d7eb9-224">En el campo Cuenta, especifique los valores deseados.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="d7eb9-225">Haga clic en Liquidar transacciones.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="d7eb9-226">Expanda la sección Totales.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="d7eb9-227">En el campo Mostrar, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="d7eb9-228">Compruebe que se han actualizado los campos Número de documento bancario y Número de envío.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="d7eb9-229">Active la casilla Marcar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="d7eb9-230">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d7eb9-230">Click OK.</span></span>
13. <span data-ttu-id="d7eb9-231">Haga clic en la ficha Pago.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="d7eb9-232">Compruebe que se han actualizado los campos Número de documento bancario y Número de envío.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="d7eb9-233">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-233">Click Post.</span></span>
15. <span data-ttu-id="d7eb9-234">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-234">Close the page.</span></span>
16. <span data-ttu-id="d7eb9-235">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="d7eb9-236">Comprobar el estado de la carta de crédito de importación tras el pago de la factura</span><span class="sxs-lookup"><span data-stu-id="d7eb9-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="d7eb9-237">Vaya a Gestión de efectivo y bancos > Carta de crédito > Importar carta de crédito e importar cobro.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="d7eb9-238">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d7eb9-239">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d7eb9-240">Compruebe el estado de la carta de crédito de importación.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="d7eb9-241">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="d7eb9-242">Comprobar el límite de crédito bancario y el informe de utilización</span><span class="sxs-lookup"><span data-stu-id="d7eb9-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="d7eb9-243">Vaya a Gestión de efectivo y bancos > Consultas e informes > Cartas de crédito o garantía > Informe de créditos bancarios y uso.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="d7eb9-244">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="d7eb9-245">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-245">Click Filter.</span></span>
    * <span data-ttu-id="d7eb9-246">Defina el campo Criterios con la cuenta bancaria necesaria.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="d7eb9-247">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="d7eb9-248">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d7eb9-249">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d7eb9-249">Click OK.</span></span>
7. <span data-ttu-id="d7eb9-250">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d7eb9-250">Click OK.</span></span>
    * <span data-ttu-id="d7eb9-251">Compruebe el informe que muestra las transacciones.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="d7eb9-252">Compruebe que el informe muestra las transacciones con número de documento bancario, límite de crédito, importe usado y el importe de saldo del crédito.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="d7eb9-253">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d7eb9-253">Close the page.</span></span>

