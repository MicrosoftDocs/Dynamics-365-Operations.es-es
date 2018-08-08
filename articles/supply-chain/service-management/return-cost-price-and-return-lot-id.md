---
title: "Precio de coste de la devolución e identificador de lote interno de devolución"
description: "Puede que desee que el coste de productos devueltos sea igual al coste que tenían los productos cuando se vendieron al cliente. Puede hacerlo utilizando el **Id. de devolución de lote**."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 33cd3d50fe342ba12a17419f4e759c243a60b3e0
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="ab8cc-104">Precio de coste de la devolución e identificador de lote interno de devolución</span><span class="sxs-lookup"><span data-stu-id="ab8cc-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="ab8cc-105">El coste de los productos que se devuelven al inventario se calcula mediante el coste actual de los productos.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="ab8cc-106">Sin embargo, puede que desee que el coste de productos devueltos sea igual al coste que tenían los productos cuando se vendieron al cliente.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="ab8cc-107">Puede hacerlo utilizando el campo **Id. de devolución de lote** de la ficha desplegable **Detalles de línea** en el formulario **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="ab8cc-108">Por ejemplo, considere el siguiente escenario.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-108">For example, consider the following scenario.</span></span> <span data-ttu-id="ab8cc-109">Envía una factura a un cliente.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-109">You invoice a customer.</span></span> <span data-ttu-id="ab8cc-110">El cliente devuelve posteriormente los productos entregados.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="ab8cc-111">Se devuelven los productos a las existencias.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-111">You return the products to stock.</span></span> <span data-ttu-id="ab8cc-112">En este caso, al abonar al cliente los productos devueltos, el coste de los productos se calcula con su coste actual.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="ab8cc-113">Sin embargo, si usa el campo **Id. de devolución de lote**, el coste de los productos devueltos se calculará con el coste de la factura de venta original del cliente.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="ab8cc-114">Para usar un coste distinto al coste actual para devoluciones de un cliente, use uno de los siguientes métodos.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="ab8cc-115">Método 1: especifique manualmente el precio de coste de devolución</span><span class="sxs-lookup"><span data-stu-id="ab8cc-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="ab8cc-116">De forma predeterminada, al agregar artículos a un pedido de devolución, los artículos se devuelven al inventario al precio de coste actual.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="ab8cc-117">Para especificar otro precio de coste de devolución, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="ab8cc-118">Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="ab8cc-119">En el **Panel de acciones**, en el grupo **Nuevo**, haga clic en **Pedido de devolución**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="ab8cc-120">En el formulario **Crear pedido de devolución**, seleccione una cuenta de cliente y, a continuación hacen clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="ab8cc-121">En el formulario **Pedido de devolución - Número de RMA: %1, %2**, seleccione un artículo y, a continuación, especifique una cantidad negativa en el campo **Cantidad**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="ab8cc-122">Haga clic en la ficha desplegable **Detalles de línea**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="ab8cc-123">En la ficha **General**, escriba un valor en el campo **Precio de coste de la devolución**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="ab8cc-124">Se usa este valor cuando las mercancías se devuelven al inventario.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="ab8cc-125">Si no especifica un valor, se usa el precio de coste actual cuando las mercancías se devuelven al inventario.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="ab8cc-126">Método 2: generar automáticamente el precio de coste según la línea de factura del cliente</span><span class="sxs-lookup"><span data-stu-id="ab8cc-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="ab8cc-127">Éste es el método preferido para crear líneas de devolución.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="ab8cc-128">Para usar el coste de los productos al momento en el que los vendió al cliente, cree un pedido de devolución y especifique la línea de ventas que desea devolver.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="ab8cc-129">Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="ab8cc-130">En el **Panel de acciones**, en el grupo **Nuevo**, haga clic en **Pedido de devolución**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="ab8cc-131">En el formulario **Crear pedido de devolución**, seleccione una cuenta de cliente y, a continuación hacen clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="ab8cc-132">En el formulario **Pedido de devolución - Número de RMA: %1, %2**, en el **Panel de acciones**, haga clic en **Buscar pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="ab8cc-133">En el formulario **Buscar pedido de ventas**, seleccione la línea de factura que desea devolver y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="ab8cc-134">En la ficha desplegable **Detalles de línea**, en la ficha **General**, el campo **Id. de devolución de lote** muestra el valor de la línea de ventas original.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="ab8cc-135">Además, el campo **Precio de coste de la devolución** muestra el valor de coste de la línea de ventas original.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="ab8cc-136">Ejemplo de cálculo de costes</span><span class="sxs-lookup"><span data-stu-id="ab8cc-136">Cost calculation example</span></span>

<span data-ttu-id="ab8cc-137">Cuando se usa el campo **Id. de devolución de lote** en una línea del pedido de devolución para especificar el precio de coste de devolución, se utiliza el coste de la línea del pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="ab8cc-138">Si ejecuta la funcionalidad de cierre o de cálculo de inventario, el coste se ajusta en la línea de ventas original.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="ab8cc-139">El coste en la línea del pedido de devolución se ajusta automáticamente para reflejar el mismo coste por unidad.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="ab8cc-140">Crear y liberar un producto que se llama Prueba.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="ab8cc-141">En el formulario **Detalles de producto emitido**, especifique la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="ab8cc-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="ab8cc-142">En la ficha desplegable **Gestionar costes**, en el campo **Grupo de artículos**, seleccione el grupo **Piezas**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="ab8cc-143">En la ficha desplegable **General**, en el campo **Grupo de modelos de artículo**, seleccione **DEF**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="ab8cc-144">En la ficha desplegable **Compra**, en el campo **Precio**, escriba 10,00 como precio de coste del artículo.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="ab8cc-145">En el **Panel de acciones**, haga clic en **Grupos de dimensiones**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="ab8cc-146">En el campo **Grupo de dimensiones de almacenamiento**, seleccione **Solo sitio y almacén**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="ab8cc-147">En el campo **Grupo de dimensiones de seguimiento**, seleccione **Ninguna dimensión de seguimiento activa**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="ab8cc-148">Crear un pedido de compra para 10 piezas del artículo Prueba a 6,00 por unidad y registre una factura para el pedido.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="ab8cc-149">Crear un segundo pedido de compra para 10 piezas del artículo Prueba a 8,00 por unidad y registre una factura para el pedido.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="ab8cc-150">Registre una factura para un pedido de ventas para vender cinco piezas del artículo Prueba.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="ab8cc-151">En este caso, la línea de pedido de ventas se calcula en 35,00 (5 piezas \* coste medio 7,00 por pieza).</span><span class="sxs-lookup"><span data-stu-id="ab8cc-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="ab8cc-152">Crear un pedido de devolución para el cliente.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-152">Create a return order for the customer.</span></span> <span data-ttu-id="ab8cc-153">En el formulario **Buscar pedido de ventas**, seleccione la línea de factura y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="ab8cc-154">En el formulario **Pedido de devolución - Número de RMA: %1, %2**, compruebe que un pedido de devolución se genera para devolver el artículo Prueba.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="ab8cc-155">La cantidad del pedido de devolución se establece en -5,00.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="ab8cc-156">El campo **Id. de devolución lote** muestra un identificador de lote.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="ab8cc-157">Este identificador de lote se obtiene del pedido de ventas original del artículo que se vendió al cliente.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="ab8cc-158">El campo **Precio de coste de la devolución** muestra el precio de coste de la línea de ventas original.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="ab8cc-159">Registe la recepción de los artículos devueltos.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="ab8cc-160">Registre un albarán para los artículos devueltos.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="ab8cc-161">Registre una factura para el pedido de devolución.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-161">Post an invoice for the return order.</span></span> <span data-ttu-id="ab8cc-162">En la página de lista **Todos los pedidos de ventas** , seleccione un pedido de ventas cuyo tipo de pedido sea **Pedido devuelto**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="ab8cc-163">Abra el formulario **Transacciones de inventario**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="ab8cc-164">Compruebe que la devolución se calcule en 7,00 por unidad con el valor del campo **Precio de coste de la devolución**, para un total de 35,00 en el campo **Importe de coste**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="ab8cc-165">Puede abrir el formulario **Transacciones de inventario** desde el formulario **Pedido de devolución - Número de RMA: %1, %2** .</span><span class="sxs-lookup"><span data-stu-id="ab8cc-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="ab8cc-166">En la cuadrícula **Líneas**, haga clic en **Inventario** \> **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="ab8cc-167">En la gestión de inventarios y almacenes, use el formulario **Cierre y ajuste** para ejecutar el procedimiento **3. Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="ab8cc-168">Esta acción ajusta el coste de la línea de ventas original que se calculó en -35,00 (5 piezas \* 7,00) en -30,00 (5 piezas \* 6,00).</span><span class="sxs-lookup"><span data-stu-id="ab8cc-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="ab8cc-169">Esto se debe a que el grupo de modelos de inventario se rige por el principio FIFO (primero en entrar, primero en salir), y 6,00 por unidad es el coste FIFO del primer pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="ab8cc-170">Además, la acción ajusta el coste de la línea de ventas de devolución para conciliar el coste por unidad en la línea de ventas original.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="ab8cc-171">Por lo tanto, el coste de la línea de devolución se ajusta de 35,00 a 30,00.</span><span class="sxs-lookup"><span data-stu-id="ab8cc-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>





