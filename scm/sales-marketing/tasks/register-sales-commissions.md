--- 
title: Registrar comisiones de ventas
description: "Este procedimiento le muestra cómo se calculan y registran las comisiones de ventas."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: f195f9e466eab3cf87afea2b5d430d0ea25c5a83
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="register-sales-commissions"></a><span data-ttu-id="563d1-103">Registrar comisiones de ventas</span><span class="sxs-lookup"><span data-stu-id="563d1-103">Register sales commissions</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="563d1-104">Este procedimiento le muestra cómo se calculan y registran las comisiones de ventas.</span><span class="sxs-lookup"><span data-stu-id="563d1-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="563d1-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="563d1-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="563d1-106">Antes de comenzar este guía, ejecute la guía llamada "Configurar reglas de comisión de ventas" para asegurarse de que tiene toda la configuración necesaria del cálculo de comisiones.</span><span class="sxs-lookup"><span data-stu-id="563d1-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="563d1-107">Anote los códigos de artículo y de cliente que ha elegido para el proceso de la comisión y úselos cuando se le solicite que crea un pedido de ventas en esta guía.</span><span class="sxs-lookup"><span data-stu-id="563d1-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="563d1-108">Facturar un pedido de ventas que califica a un vendedor para una comisión</span><span class="sxs-lookup"><span data-stu-id="563d1-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="563d1-109">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="563d1-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="563d1-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="563d1-110">Click New.</span></span>
3. <span data-ttu-id="563d1-111">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="563d1-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="563d1-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="563d1-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="563d1-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="563d1-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="563d1-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="563d1-114">Click OK.</span></span>
7. <span data-ttu-id="563d1-115">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="563d1-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="563d1-116">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="563d1-116">Click Change view.</span></span>
9. <span data-ttu-id="563d1-117">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="563d1-117">Click Header view.</span></span>
10. <span data-ttu-id="563d1-118">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="563d1-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="563d1-119">El valor del campo Grupo de ventas representa un grupo con uno o varios representantes de ventas asignados.</span><span class="sxs-lookup"><span data-stu-id="563d1-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="563d1-120">Las personas del grupo son las que recibirán comisiones cuando se facture el pedido, según las cuotas y distribución predefinidas.</span><span class="sxs-lookup"><span data-stu-id="563d1-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="563d1-121">El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.</span><span class="sxs-lookup"><span data-stu-id="563d1-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="563d1-122">El grupo de ventas también se copia en la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="563d1-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="563d1-123">Puede cambiarlo de modo que pueda ser diferente del que se encuentra en el encabezado y/o entre las líneas.</span><span class="sxs-lookup"><span data-stu-id="563d1-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="563d1-124">El valor del campo Grupo de comisión representa un grupo que ha creado para uno o más clientes con el propósito de realizar el seguimiento de las comisiones.</span><span class="sxs-lookup"><span data-stu-id="563d1-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="563d1-125">El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.</span><span class="sxs-lookup"><span data-stu-id="563d1-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="563d1-126">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="563d1-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="563d1-127">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="563d1-127">Click Change view.</span></span>
13. <span data-ttu-id="563d1-128">Haga clic en Vista de líneas.</span><span class="sxs-lookup"><span data-stu-id="563d1-128">Click Line view.</span></span>
14. <span data-ttu-id="563d1-129">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="563d1-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="563d1-130">En la lista, seleccione el artículo que se ha configurado para las comisiones.</span><span class="sxs-lookup"><span data-stu-id="563d1-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="563d1-131">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="563d1-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="563d1-132">Anote el importe neto de la línea.</span><span class="sxs-lookup"><span data-stu-id="563d1-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="563d1-133">Representa el ingreso de ventas, que en este ejemplo es la base para el cálculo de la comisión.</span><span class="sxs-lookup"><span data-stu-id="563d1-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="563d1-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="563d1-134">Click Save.</span></span>
18. <span data-ttu-id="563d1-135">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="563d1-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="563d1-136">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="563d1-136">Click Invoice.</span></span>
20. <span data-ttu-id="563d1-137">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="563d1-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="563d1-138">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="563d1-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="563d1-139">Seleccione Sí en el campo Registro.</span><span class="sxs-lookup"><span data-stu-id="563d1-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="563d1-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="563d1-140">Click OK.</span></span>
24. <span data-ttu-id="563d1-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="563d1-141">Click OK.</span></span>
    * <span data-ttu-id="563d1-142">Se puede tardar un minuto aproximadamente en registrar la transacción.</span><span class="sxs-lookup"><span data-stu-id="563d1-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="563d1-143">Deje que se complete el procesamiento y no cierre la página.</span><span class="sxs-lookup"><span data-stu-id="563d1-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="563d1-144">Revise las comisiones de ventas registradas</span><span class="sxs-lookup"><span data-stu-id="563d1-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="563d1-145">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="563d1-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="563d1-146">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="563d1-146">Click Invoice.</span></span>
3. <span data-ttu-id="563d1-147">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="563d1-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="563d1-148">Haga clic en Transacciones de comisión.</span><span class="sxs-lookup"><span data-stu-id="563d1-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="563d1-149">La ficha Visión general muestra líneas que representan los importes de la comisión que se deben pagar a los representantes de ventas asociados al pedido de ventas facturado.</span><span class="sxs-lookup"><span data-stu-id="563d1-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="563d1-150">Revisemos la información.</span><span class="sxs-lookup"><span data-stu-id="563d1-150">Let's review the details.</span></span>     
    * <span data-ttu-id="563d1-151">Si ha usado la guía "Configurar reglas de comisión de ventas" para configurar el Grupo de ventas de la comisión, hay dos vendedores que recibirán una comisión de ventas y la comisión se dividirá de manera igualitaria entre ellos.</span><span class="sxs-lookup"><span data-stu-id="563d1-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="563d1-152">En este ejemplo, se calcula el importe total de la comisión como porcentaje de los ingresos de ventas (el importe neto de la línea de pedido).</span><span class="sxs-lookup"><span data-stu-id="563d1-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="563d1-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="563d1-153">Close the page.</span></span>
6. <span data-ttu-id="563d1-154">Haga clic en Asiento.</span><span class="sxs-lookup"><span data-stu-id="563d1-154">Click Voucher.</span></span>
    * <span data-ttu-id="563d1-155">Puede revisar las transacciones de asiento para los importes de comisión que se han registrado en el gasto de la comisión predefinido y las cuentas de proveedores de la comisión.</span><span class="sxs-lookup"><span data-stu-id="563d1-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


