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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 0fad3c62f926e508e09a265a600194b7ea595bf0
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="register-sales-commissions"></a><span data-ttu-id="70ab7-103">Registrar comisiones de ventas</span><span class="sxs-lookup"><span data-stu-id="70ab7-103">Register sales commissions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="70ab7-104">Este procedimiento le muestra cómo se calculan y registran las comisiones de ventas.</span><span class="sxs-lookup"><span data-stu-id="70ab7-104">This procedure shows you how sales commissions are calculated and registered.</span></span> <span data-ttu-id="70ab7-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="70ab7-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="70ab7-106">Antes de comenzar este guía, ejecute la guía llamada "Configurar reglas de comisión de ventas" para asegurarse de que tiene toda la configuración necesaria del cálculo de comisiones.</span><span class="sxs-lookup"><span data-stu-id="70ab7-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="70ab7-107">Anote los códigos de artículo y de cliente que ha elegido para el proceso de la comisión y úselos cuando se le solicite que crea un pedido de ventas en esta guía.</span><span class="sxs-lookup"><span data-stu-id="70ab7-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="70ab7-108">Facturar un pedido de ventas que califica a un vendedor para una comisión</span><span class="sxs-lookup"><span data-stu-id="70ab7-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="70ab7-109">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="70ab7-109">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="70ab7-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="70ab7-110">Click New.</span></span>
3. <span data-ttu-id="70ab7-111">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="70ab7-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="70ab7-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="70ab7-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="70ab7-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="70ab7-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="70ab7-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="70ab7-114">Click OK.</span></span>
7. <span data-ttu-id="70ab7-115">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="70ab7-115">On the Action Pane, click Options.</span></span>
8. <span data-ttu-id="70ab7-116">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="70ab7-116">Click Change view.</span></span>
9. <span data-ttu-id="70ab7-117">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="70ab7-117">Click Header view.</span></span>
10. <span data-ttu-id="70ab7-118">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="70ab7-118">Expand the Setup section.</span></span>
    * <span data-ttu-id="70ab7-119">El valor del campo Grupo de ventas representa un grupo con uno o varios representantes de ventas asignados.</span><span class="sxs-lookup"><span data-stu-id="70ab7-119">The value in the Sales group field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="70ab7-120">Las personas del grupo son las que recibirán comisiones cuando se facture el pedido, según las cuotas y distribución predefinidas.</span><span class="sxs-lookup"><span data-stu-id="70ab7-120">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   <span data-ttu-id="70ab7-121">El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.</span><span class="sxs-lookup"><span data-stu-id="70ab7-121">The value is copied from the Customer card, but you can change it if you wish.</span></span>  <span data-ttu-id="70ab7-122">El grupo de ventas también se copia en la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="70ab7-122">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="70ab7-123">Puede cambiarlo de modo que pueda ser diferente del que se encuentra en el encabezado y/o entre las líneas.</span><span class="sxs-lookup"><span data-stu-id="70ab7-123">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    * <span data-ttu-id="70ab7-124">El valor del campo Grupo de comisión representa un grupo que ha creado para uno o más clientes con el propósito de realizar el seguimiento de las comisiones.</span><span class="sxs-lookup"><span data-stu-id="70ab7-124">The value in the Commission group field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   <span data-ttu-id="70ab7-125">El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.</span><span class="sxs-lookup"><span data-stu-id="70ab7-125">The value is copied from the Customer card, but you can change it if you wish.</span></span>   
11. <span data-ttu-id="70ab7-126">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="70ab7-126">On the Action Pane, click Options.</span></span>
12. <span data-ttu-id="70ab7-127">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="70ab7-127">Click Change view.</span></span>
13. <span data-ttu-id="70ab7-128">Haga clic en Vista de líneas.</span><span class="sxs-lookup"><span data-stu-id="70ab7-128">Click Line view.</span></span>
14. <span data-ttu-id="70ab7-129">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="70ab7-129">In the Item number field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="70ab7-130">En la lista, seleccione el artículo que se ha configurado para las comisiones.</span><span class="sxs-lookup"><span data-stu-id="70ab7-130">In the list, select the item you have set up for commissions.</span></span> 
16. <span data-ttu-id="70ab7-131">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="70ab7-131">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="70ab7-132">Anote el importe neto de la línea.</span><span class="sxs-lookup"><span data-stu-id="70ab7-132">Take note of the line's Net amount.</span></span> <span data-ttu-id="70ab7-133">Representa el ingreso de ventas, que en este ejemplo es la base para el cálculo de la comisión.</span><span class="sxs-lookup"><span data-stu-id="70ab7-133">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
17. <span data-ttu-id="70ab7-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="70ab7-134">Click Save.</span></span>
18. <span data-ttu-id="70ab7-135">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="70ab7-135">On the Action Pane, click Invoice.</span></span>
19. <span data-ttu-id="70ab7-136">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="70ab7-136">Click Invoice.</span></span>
20. <span data-ttu-id="70ab7-137">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="70ab7-137">Expand the Parameters section.</span></span>
21. <span data-ttu-id="70ab7-138">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="70ab7-138">In the Quantity field, select 'All'.</span></span>
22. <span data-ttu-id="70ab7-139">Seleccione Sí en el campo Registro.</span><span class="sxs-lookup"><span data-stu-id="70ab7-139">Select Yes in the Posting field.</span></span>
23. <span data-ttu-id="70ab7-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="70ab7-140">Click OK.</span></span>
24. <span data-ttu-id="70ab7-141">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="70ab7-141">Click OK.</span></span>
    * <span data-ttu-id="70ab7-142">Se puede tardar un minuto aproximadamente en registrar la transacción.</span><span class="sxs-lookup"><span data-stu-id="70ab7-142">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="70ab7-143">Deje que se complete el procesamiento y no cierre la página.</span><span class="sxs-lookup"><span data-stu-id="70ab7-143">Allow the processing to complete and don’t close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="70ab7-144">Revise las comisiones de ventas registradas</span><span class="sxs-lookup"><span data-stu-id="70ab7-144">Review the registered sales commissions</span></span>
1. <span data-ttu-id="70ab7-145">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="70ab7-145">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="70ab7-146">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="70ab7-146">Click Invoice.</span></span>
3. <span data-ttu-id="70ab7-147">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="70ab7-147">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="70ab7-148">Haga clic en Transacciones de comisión.</span><span class="sxs-lookup"><span data-stu-id="70ab7-148">Click Commission transactions.</span></span>
    * <span data-ttu-id="70ab7-149">La ficha Visión general muestra líneas que representan los importes de la comisión que se deben pagar a los representantes de ventas asociados al pedido de ventas facturado.</span><span class="sxs-lookup"><span data-stu-id="70ab7-149">The Overview tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="70ab7-150">Revisemos la información.</span><span class="sxs-lookup"><span data-stu-id="70ab7-150">Let's review the details.</span></span>     
    * <span data-ttu-id="70ab7-151">Si ha usado la guía "Configurar reglas de comisión de ventas" para configurar el Grupo de ventas de la comisión, hay dos vendedores que recibirán una comisión de ventas y la comisión se dividirá de manera igualitaria entre ellos.</span><span class="sxs-lookup"><span data-stu-id="70ab7-151">If you used the "Set up sales commission rules" guide to set up the Commission sales group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    * <span data-ttu-id="70ab7-152">En este ejemplo, se calcula el importe total de la comisión como porcentaje de los ingresos de ventas (el importe neto de la línea de pedido).</span><span class="sxs-lookup"><span data-stu-id="70ab7-152">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>   
5. <span data-ttu-id="70ab7-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="70ab7-153">Close the page.</span></span>
6. <span data-ttu-id="70ab7-154">Haga clic en Asiento.</span><span class="sxs-lookup"><span data-stu-id="70ab7-154">Click Voucher.</span></span>
    * <span data-ttu-id="70ab7-155">Puede revisar las transacciones de asiento para los importes de comisión que se han registrado en el gasto de la comisión predefinido y las cuentas de proveedores de la comisión.</span><span class="sxs-lookup"><span data-stu-id="70ab7-155">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  


