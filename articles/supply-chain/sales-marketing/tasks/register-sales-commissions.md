---
title: Registrar comisiones de ventas
description: En este tema se explica cómo se calculan y registran las comisiones de ventas.
author: omulvad
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher, CustClassificationGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee75f3a0c9dea7a7c4a4f927651aaab1d6bdb5c0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836383"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="53e16-103">Registrar comisiones de ventas</span><span class="sxs-lookup"><span data-stu-id="53e16-103">Register sales commissions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53e16-104">En este tema se explica cómo se calculan y registran las comisiones de ventas.</span><span class="sxs-lookup"><span data-stu-id="53e16-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="53e16-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="53e16-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="53e16-106">Antes de comenzar este guía, ejecute la guía llamada "Configurar reglas de comisión de ventas" para asegurarse de que tiene toda la configuración necesaria del cálculo de comisiones.</span><span class="sxs-lookup"><span data-stu-id="53e16-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="53e16-107">Anote los códigos de artículo y de cliente que ha elegido para el proceso de la comisión y úselos cuando se le solicite que crea un pedido de ventas en esta guía.</span><span class="sxs-lookup"><span data-stu-id="53e16-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="53e16-108">Facturar un pedido de ventas que califica a un vendedor para una comisión</span><span class="sxs-lookup"><span data-stu-id="53e16-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="53e16-109">En el panel de navegación, vaya a **Módulos > > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="53e16-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="53e16-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53e16-110">Select **New**.</span></span>
3. <span data-ttu-id="53e16-111">En el campo **Cuenta de cliente**, seleccione el registro deseado desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="53e16-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="53e16-112">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="53e16-112">Select **OK**.</span></span>
5. <span data-ttu-id="53e16-113">En el panel de acciones, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="53e16-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="53e16-114">Seleccione **Cambiar vista**.</span><span class="sxs-lookup"><span data-stu-id="53e16-114">Select **Change view**.</span></span>
7. <span data-ttu-id="53e16-115">Seleccione **Visualización de encabezado**.</span><span class="sxs-lookup"><span data-stu-id="53e16-115">Select **Header view**.</span></span>
8. <span data-ttu-id="53e16-116">Expanda la sección **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="53e16-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="53e16-117">El valor del campo **Grupo de ventas** representa un grupo con uno o varios representantes de ventas asignados.</span><span class="sxs-lookup"><span data-stu-id="53e16-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="53e16-118">Las personas del grupo son las que recibirán comisiones cuando se facture el pedido, según las cuotas y distribución predefinidas.</span><span class="sxs-lookup"><span data-stu-id="53e16-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="53e16-119">El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.</span><span class="sxs-lookup"><span data-stu-id="53e16-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="53e16-120">El grupo de ventas también se copia en la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53e16-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="53e16-121">Puede cambiarlo de modo que pueda ser diferente del que se encuentra en el encabezado y/o entre las líneas.</span><span class="sxs-lookup"><span data-stu-id="53e16-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="53e16-122">El valor del campo **Grupo de comisión** representa un grupo que ha creado para uno o más clientes con el propósito de realizar el seguimiento de las comisiones.</span><span class="sxs-lookup"><span data-stu-id="53e16-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="53e16-123">El valor se copia de la Tarjeta de cliente, pero puede cambiarlo si lo desea.</span><span class="sxs-lookup"><span data-stu-id="53e16-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="53e16-124">En el panel de acciones, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="53e16-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="53e16-125">Seleccione **Cambiar vista**.</span><span class="sxs-lookup"><span data-stu-id="53e16-125">Select **Change view**.</span></span>
11. <span data-ttu-id="53e16-126">Seleccione **Vista de líneas**.</span><span class="sxs-lookup"><span data-stu-id="53e16-126">Select **Line view**.</span></span>
12. <span data-ttu-id="53e16-127">En el menú desplegable del campo **Código de artículo**, seleccione el artículo que haya configurado para las comisiones.</span><span class="sxs-lookup"><span data-stu-id="53e16-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="53e16-128">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="53e16-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="53e16-129">Anote el importe neto de la línea.</span><span class="sxs-lookup"><span data-stu-id="53e16-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="53e16-130">Representa el ingreso de ventas, que en este ejemplo es la base para el cálculo de la comisión.</span><span class="sxs-lookup"><span data-stu-id="53e16-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="53e16-131">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53e16-131">Select **Save**.</span></span>
15. <span data-ttu-id="53e16-132">En el Panel de acciones, seleccione **Factura**.</span><span class="sxs-lookup"><span data-stu-id="53e16-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="53e16-133">Seleccionar **Facturas**.</span><span class="sxs-lookup"><span data-stu-id="53e16-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="53e16-134">Expanda la sección **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="53e16-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="53e16-135">En el campo **Cantidad**, seleccione **Todo**.</span><span class="sxs-lookup"><span data-stu-id="53e16-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="53e16-136">Seleccione **Sí** en el campo **Registro**.</span><span class="sxs-lookup"><span data-stu-id="53e16-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="53e16-137">Seleccione **Aceptar** y, a continuación, seleccione **Aceptar** en el panel siguiente.</span><span class="sxs-lookup"><span data-stu-id="53e16-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="53e16-138">Se puede tardar un minuto aproximadamente en registrar la transacción.</span><span class="sxs-lookup"><span data-stu-id="53e16-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="53e16-139">Deje que se complete el procesamiento y no cierre la página.</span><span class="sxs-lookup"><span data-stu-id="53e16-139">Allow the processing to complete and don't close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="53e16-140">Revise las comisiones de ventas registradas</span><span class="sxs-lookup"><span data-stu-id="53e16-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="53e16-141">En el panel de acciones, seleccione **Factura** y, a continuación, vuelva a seleccionar **Factura**.</span><span class="sxs-lookup"><span data-stu-id="53e16-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="53e16-142">En el panel de acciones, seleccione **Factura** y, a continuación, seleccione **Transacciones de comisión**.</span><span class="sxs-lookup"><span data-stu-id="53e16-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="53e16-143">La pestaña **Visión general** muestra líneas que representan los importes de la comisión que se deben pagar a los representantes de ventas asociados al pedido de ventas facturado.</span><span class="sxs-lookup"><span data-stu-id="53e16-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="53e16-144">Revisemos la información.</span><span class="sxs-lookup"><span data-stu-id="53e16-144">Let's review the details.</span></span>  
    - <span data-ttu-id="53e16-145">Si ha usado la guía "Configurar reglas de comisión de ventas" para configurar el Grupo de **ventas de la comisión**, hay dos vendedores que recibirán una comisión de ventas y la comisión se dividirá de manera igualitaria entre ellos.</span><span class="sxs-lookup"><span data-stu-id="53e16-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="53e16-146">En este ejemplo, se calcula el importe total de la comisión como porcentaje de los ingresos de ventas (el importe neto de la línea de pedido).</span><span class="sxs-lookup"><span data-stu-id="53e16-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="53e16-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="53e16-147">Close the page.</span></span>
4. <span data-ttu-id="53e16-148">Seleccione **Asiento**.</span><span class="sxs-lookup"><span data-stu-id="53e16-148">Select **Voucher**.</span></span> <span data-ttu-id="53e16-149">Puede revisar las transacciones de asiento para los importes de comisión que se han registrado en el gasto de la comisión predefinido y las cuentas de proveedores de la comisión.</span><span class="sxs-lookup"><span data-stu-id="53e16-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]