---
title: Confirmar pedidos de ventas
description: Este procedimiento muestra cómo confirmar pedidos de ventas.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesTable, SalesEditLines,  SrsReportViewerForm, CustConfirmJournal, SysQueryForm, SysQueryFieldLookUp, SysLookup, SalesParmIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db475cf967bebec2d442aaa864800d920cf0ab81
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564003"
---
# <a name="confirm-sales-orders"></a><span data-ttu-id="a1a44-103">Confirmar pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="a1a44-103">Confirm sales orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a1a44-104">Este procedimiento muestra cómo confirmar pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-104">This procedure demonstrates how to confirm sales orders.</span></span> <span data-ttu-id="a1a44-105">Se le mostrará cómo confirmar un solo pedido y cómo confirmar varios pedidos de una vez.</span><span class="sxs-lookup"><span data-stu-id="a1a44-105">You’ll be shown how to confirm a single order, and how to confirm multiple orders at once.</span></span> <span data-ttu-id="a1a44-106">Estas tareas las realizará normalmente la persona encargada de procesar los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-106">These tasks would typically be carried out by a sales order processor.</span></span> <span data-ttu-id="a1a44-107">Puede utilizar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="a1a44-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="a1a44-108">Antes de empezar, asegúrese de que haya varios pedidos de ventas abiertos para el mismo cliente.</span><span class="sxs-lookup"><span data-stu-id="a1a44-108">Before you start, make sure there are several open sales orders for the same customer.</span></span> <span data-ttu-id="a1a44-109">Si está usando USMF, puede usar el cliente US-027.</span><span class="sxs-lookup"><span data-stu-id="a1a44-109">If you’re using USMF, you can use customer US-027.</span></span>


## <a name="confirm-a-single-sales-order"></a><span data-ttu-id="a1a44-110">Confirmación de un solo pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="a1a44-110">Confirm a single sales order</span></span>
1. <span data-ttu-id="a1a44-111">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-111">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="a1a44-112">En la lista, busque y seleccione el pedido que desee confirmar.</span><span class="sxs-lookup"><span data-stu-id="a1a44-112">In the list, find and select the order that you want to confirm.</span></span>
3. <span data-ttu-id="a1a44-113">Haga clic en el vínculo en el número de pedido de ventas para abrir el pedido seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a1a44-113">Click the link on the sales order number to open the selected order.</span></span>
4. <span data-ttu-id="a1a44-114">En el panel de acciones, haga clic en Vender.</span><span class="sxs-lookup"><span data-stu-id="a1a44-114">On the Action Pane, click Sell.</span></span>
5. <span data-ttu-id="a1a44-115">Haga clic en Confirmar pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-115">Click Confirm sales order.</span></span>
6. <span data-ttu-id="a1a44-116">Expanda o contraiga la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="a1a44-116">Expand or collapse the Parameters section.</span></span>
    * <span data-ttu-id="a1a44-117">Asegúrese de que el campo de confirmación de registro esté activo.</span><span class="sxs-lookup"><span data-stu-id="a1a44-117">Make sure that the Posting Yes field is active.</span></span>  
7. <span data-ttu-id="a1a44-118">Establezca la opción Imprimir confirmación en Sí.</span><span class="sxs-lookup"><span data-stu-id="a1a44-118">Set the Print confirmation option to Yes.</span></span>
    * <span data-ttu-id="a1a44-119">El campo Comprobar límite de crédito especifica el método que se usa para calcular el crédito que le queda a un cliente.</span><span class="sxs-lookup"><span data-stu-id="a1a44-119">The Check credit limit field specifies the method that’s used to calculate a customer's remaining credit.</span></span> <span data-ttu-id="a1a44-120">De forma predeterminada, se copia desde la página Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="a1a44-120">By default, it’s copied from the Accounts receivable parameters page.</span></span> <span data-ttu-id="a1a44-121">Si desea omitir la comprobación del límite de crédito al confirmar un pedido de ventas específico, defina Comprobar límite de crédito en Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a1a44-121">If you want to skip the credit limit check when confirming a specific sales order, set the Check credit limit to None.</span></span> <span data-ttu-id="a1a44-122">No obstante, debe tener presente que, incluso si este campo está establecido en Ninguno, la comprobación del límite de crédito se seguirá realizando si la opción Límite de crédito obligatorio está seleccionada en los datos maestros del cliente.</span><span class="sxs-lookup"><span data-stu-id="a1a44-122">However, you should be aware that even with if this field is set to None, the credit limit check will still be performed if the Mandatory credit limit option is selected on the customer master data.</span></span>  
8. <span data-ttu-id="a1a44-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a1a44-123">Click OK.</span></span>
9. <span data-ttu-id="a1a44-124">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="a1a44-124">Click Yes.</span></span>
10. <span data-ttu-id="a1a44-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a1a44-125">Close the page.</span></span>
11. <span data-ttu-id="a1a44-126">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="a1a44-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="a1a44-127">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="a1a44-127">Click Change view.</span></span>
13. <span data-ttu-id="a1a44-128">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="a1a44-128">Click Header view.</span></span>
    * <span data-ttu-id="a1a44-129">Cuando se confirma un pedido, el estado del documento se establece en Confirmación.</span><span class="sxs-lookup"><span data-stu-id="a1a44-129">When an order is confirmed, the Document status is set to Confirmation.</span></span>  
14. <span data-ttu-id="a1a44-130">En el panel de acciones, haga clic en Vender.</span><span class="sxs-lookup"><span data-stu-id="a1a44-130">On the Action Pane, click Sell.</span></span>
15. <span data-ttu-id="a1a44-131">Haga clic en Confirmación del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-131">Click Sales order confirmation.</span></span>
16. <span data-ttu-id="a1a44-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a1a44-132">Close the page.</span></span>

## <a name="confirm-multiple-sales-orders-at-once"></a><span data-ttu-id="a1a44-133">Confirmación de varios pedidos de ventas a la vez</span><span class="sxs-lookup"><span data-stu-id="a1a44-133">Confirm multiple sales orders at once</span></span>
1. <span data-ttu-id="a1a44-134">Vaya a Ventas y marketing > Pedidos de ventas > Confirmación de pedido > Confirmar pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-134">Go to Sales and marketing > Sales orders > Order confirmation > Confirm sales order.</span></span>
2. <span data-ttu-id="a1a44-135">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="a1a44-135">Click Select.</span></span>
3. <span data-ttu-id="a1a44-136">En la lista de la ficha Rango, localice y seleccione el registro que hace referencia al campo Cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="a1a44-136">In the list on the Range tab, find and select the record that references the Customer account field.</span></span>
4. <span data-ttu-id="a1a44-137">En el campo Criterios, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a1a44-137">In the Criteria field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="a1a44-138">En la lista, busque y seleccione la cuenta de cliente con los varios pedidos que desea confirmar en masa.</span><span class="sxs-lookup"><span data-stu-id="a1a44-138">In the list, find and select the customer account that has multiple orders which you want to mass confirm.</span></span>
    * <span data-ttu-id="a1a44-139">Si está usando USMF, puede seleccionar la cuenta US-027.</span><span class="sxs-lookup"><span data-stu-id="a1a44-139">If you’re using USMF, you can select account US-027.</span></span>  
6. <span data-ttu-id="a1a44-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a1a44-140">Click OK.</span></span>
    * <span data-ttu-id="a1a44-141">La ficha Visión general muestra una lista de los pedidos que coinciden con los criterios de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a1a44-141">The Overview tab displays a list of the orders that match the query criteria.</span></span> <span data-ttu-id="a1a44-142">Estos se incluirán en la confirmación.</span><span class="sxs-lookup"><span data-stu-id="a1a44-142">These will be included in the confirmation.</span></span>  
    * <span data-ttu-id="a1a44-143">El campo Actualización conjunta para especifica el parámetro por el cual se reunirán varios pedidos en un documento de confirmación.</span><span class="sxs-lookup"><span data-stu-id="a1a44-143">The Summary update for field specifies the parameter by which multiple orders are to be summarized into one confirmation document.</span></span> <span data-ttu-id="a1a44-144">De forma predeterminada, la opción se copia de los valores predeterminados del ajuste de actualización conjunta en la página Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="a1a44-144">By default, the option is copied from the Default values for summary update setting on the Accounts receivable parameters page.</span></span>  
7. <span data-ttu-id="a1a44-145">En el campo Actualización conjunta para, seleccione Pedido.</span><span class="sxs-lookup"><span data-stu-id="a1a44-145">In the Summary update for field, select 'Order'.</span></span>
    * <span data-ttu-id="a1a44-146">Los parámetros mínimos requeridos para crear actualizaciones conjuntas son la cuenta de facturación y la divisa.</span><span class="sxs-lookup"><span data-stu-id="a1a44-146">The minimum parameters that are required to create summary updates are Invoice account and Currency.</span></span> <span data-ttu-id="a1a44-147">Esto significa que no se permiten actualizaciones conjuntas con diferentes cuentas de facturación y divisas.</span><span class="sxs-lookup"><span data-stu-id="a1a44-147">This means that summary updates that have different invoice accounts and different currencies are not allowed.</span></span> <span data-ttu-id="a1a44-148">Se pueden configurar parámetros adicionales en la página Parámetros de actualización conjunta, disponible desde la página Parámetros de clientes.</span><span class="sxs-lookup"><span data-stu-id="a1a44-148">Additional parameters can be set up in the Summary update parameters page which is accessible from the Accounts receivable parameters page.</span></span>  
8. <span data-ttu-id="a1a44-149">En el campo Pedido de ventas, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a1a44-149">In the Sales order field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="a1a44-150">En la lista, seleccione el número del pedido que desea que sea el pedido de resumen.</span><span class="sxs-lookup"><span data-stu-id="a1a44-150">In the list, select the order number that you want to be the summary order.</span></span>
10. <span data-ttu-id="a1a44-151">Haga clic en Organizar.</span><span class="sxs-lookup"><span data-stu-id="a1a44-151">Click Arrange.</span></span>
11. <span data-ttu-id="a1a44-152">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a1a44-152">Click OK.</span></span>
12. <span data-ttu-id="a1a44-153">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a1a44-153">Click OK.</span></span>

