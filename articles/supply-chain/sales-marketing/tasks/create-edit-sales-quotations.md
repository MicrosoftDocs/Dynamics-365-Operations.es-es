--- 
title: Crear y editar presupuestos de ventas
description: "Este procedimiento muestra cómo crear y actualizar un presupuesto de ventas."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SalesQuotationTotals, SalesQuotationPriceSimulation, SalesQuotationEditLines, SrsReportViewerForm, smmSetNumSeqIfManual, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: c5e7164633bbb33b436ab7a6fcd8ff62183c6eb5
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="create-and-edit-sales-quotations"></a><span data-ttu-id="6a4d9-103">Crear y editar presupuestos de ventas</span><span class="sxs-lookup"><span data-stu-id="6a4d9-103">Create and edit sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6a4d9-104">Este procedimiento muestra cómo crear y actualizar un presupuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-104">This procedure demonstrates how to create and update a sales quotation.</span></span> <span data-ttu-id="6a4d9-105">Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-105">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-sales-quotation"></a><span data-ttu-id="6a4d9-106">Crear un presupuesto de ventas</span><span class="sxs-lookup"><span data-stu-id="6a4d9-106">Create a sales quotation</span></span>
1. <span data-ttu-id="6a4d9-107">Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-107">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
2. <span data-ttu-id="6a4d9-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-108">Click New.</span></span>
3. <span data-ttu-id="6a4d9-109">En el campo Tipo de cuenta, seleccione "Cliente potencial".</span><span class="sxs-lookup"><span data-stu-id="6a4d9-109">In the Account type field, select 'Prospect'.</span></span>
4. <span data-ttu-id="6a4d9-110">En el campo Cliente potencial, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-110">In the Prospect field, enter or select a value.</span></span>
5. <span data-ttu-id="6a4d9-111">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-111">Expand the General section.</span></span>
    * <span data-ttu-id="6a4d9-112">Dado que ha elegido crear un presupuesto del área Ventas y marketing, el tipo se establece automáticamente en Presupuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-112">Because you chose to create a quotation from the Sales and Marketing area, the type is automatically set to Sales quotation.</span></span> <span data-ttu-id="6a4d9-113">Para crear un presupuesto para un proyecto, debe obtener acceso a él en el módulo de Gestión de proyectos y contabilidad.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-113">To create a quotation for a project you must access it from the Project management and accounting module.</span></span>   
6. <span data-ttu-id="6a4d9-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6a4d9-114">Click OK.</span></span>
    * <span data-ttu-id="6a4d9-115">Los campos y las acciones de las líneas de presupuesto son muy similares a los que se encuentran en las líneas de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-115">The fields and actions on the quotation lines are very similar to the ones on the sales order lines.</span></span>   <span data-ttu-id="6a4d9-116">Como los pedidos de ventas, los presupuestos se pueden crear para un artículo específico o, cuando no se conoce el número de artículo o no existe en el momento de la creación de presupuestos, los presupuestos se pueden crear para una categoría de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-116">Like sales orders, quotations can be created for a specific item or, when item number is not known or does not exist at the time of quotation creation, quotations can be created for a sales category.</span></span>  
7. <span data-ttu-id="6a4d9-117">En el campo Artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-117">In the Item field, enter or select a value.</span></span>
8. <span data-ttu-id="6a4d9-118">En el campo Artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-118">In the Item field, type a value.</span></span>
9. <span data-ttu-id="6a4d9-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-119">Close the page.</span></span>
10. <span data-ttu-id="6a4d9-120">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-120">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="6a4d9-121">Si hay acuerdos comerciales válidos para el artículo seleccionado en la línea, los precios y los descuentos aplicables se copiarán automáticamente a la línea de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-121">If there are valid trade agreements for the item selected on the line, the applicable price and discounts will be automatically copied to the quotation line.</span></span> <span data-ttu-id="6a4d9-122">Asegúrese de que el campo Precio unitario contiene un valor y también puede especificar valores de descuento si lo desea.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-122">Make sure that the Unit price field contains a value and you can also enter discount values if you want to.</span></span>  
11. <span data-ttu-id="6a4d9-123">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-123">Click Save.</span></span>
12. <span data-ttu-id="6a4d9-124">En el panel de acciones, haga clic en Presupuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-124">On the Action Pane, click Sales quotation.</span></span>
13. <span data-ttu-id="6a4d9-125">Haga clic en Totales.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-125">Click Totals.</span></span>
14. <span data-ttu-id="6a4d9-126">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6a4d9-126">Click OK.</span></span>
15. <span data-ttu-id="6a4d9-127">Haga clic en Línea de presupuesto de venta.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-127">Click Sales quotation line.</span></span>
16. <span data-ttu-id="6a4d9-128">Haga clic en Precios.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-128">Click Prices.</span></span>
    * <span data-ttu-id="6a4d9-129">En la página Ejecutar simulación de precios puede experimentar con el ajuste de ingresos o rentabilidad previstos de su presupuesto según el precio unitario que desee, el importe del descuento, el porcentaje del descuento, el importe total, el margen o el coeficiente de contribución.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-129">In the Run price simulation page you can experiment with adjusting the expected revenue or profitability of your quotation based on the desired unit price, discount amount, discount percentage, total amount, margin, or contribution ratio.</span></span>   <span data-ttu-id="6a4d9-130">Cuando esté satisfecho con las cifras de destino, aplique la sugerencia a la línea de presupuesto y sus campos relacionados con precios se actualizarán en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-130">When you are satisfied with the target figures, you apply the suggestion to the quotation line, and its price-related fields will be updated accordingly.</span></span>  
    * <span data-ttu-id="6a4d9-131">Puede crear tantas simulaciones de precios como desee.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-131">Y ou can create as many price simulations as you wish.</span></span> <span data-ttu-id="6a4d9-132">Al hacer clic en Nuevo, las condiciones de precios de la línea de presupuesto actual se copian en la página.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-132">When you click New, the price conditions from the current quotation line are copied to the page.</span></span> <span data-ttu-id="6a4d9-133">A continuación puede modificar los valores de cualquiera de los campos relacionados con precios cualquiera con los de destino.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-133">You can then modify values in any of the price-related fields to the target ones.</span></span> <span data-ttu-id="6a4d9-134">Un cambio en uno de los campos accionará el recálculo en todos los demás campos.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-134">A change in one of the fields will trigger recalculation in all the other fields.</span></span> <span data-ttu-id="6a4d9-135">Para que el sistema calcule el margen de ventas y el coeficiente de contribución, se tiene que conocer el coste unitario del producto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-135">In order for the system to calculate the sales margin and contribution ratio, the product's unit cost has to be known.</span></span> <span data-ttu-id="6a4d9-136">Use la ficha Precios simulados para obtener una vista detallada de los precios originales, los cambios propuestos y su efecto en los totales del presupuesto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-136">Use the Simulated prices tab for a detailed view of the original prices, proposed changes and their effect on the quotation totals.</span></span>   <span data-ttu-id="6a4d9-137">Como regla general, cuando una simulación que establece un nuevo importe se aplica a la línea de presupuesto, el sistema vuelve a realizar el cálculo y especifica un valor nuevo en el campo Precio unitario.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-137">As a general rule, when a simulation that sets a new amount is applied to the quotation line, the system recalculates and enters a new value in the Unit price field.</span></span> <span data-ttu-id="6a4d9-138">Si la simulación se basa en un nuevo margen o un nuevo coeficiente de contribución, solo se actualiza el campo Importe neto y el Precio unitario está en blanco.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-138">If the simulation is based on a new margin or a new contribution ratio, only the Net amount field is updated, and the Unit price is blank.</span></span> <span data-ttu-id="6a4d9-139">En ambos casos, se eliminará los descuentos que se encontraban en la línea de presupuesto antes de la simulación.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-139">In both cases, any discounts that were on the quotation line before simulation will be deleted.</span></span>  
17. <span data-ttu-id="6a4d9-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-140">Close the page.</span></span>
18. <span data-ttu-id="6a4d9-141">En el panel de acciones, haga clic en Presupuesto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-141">On the Action Pane, click Quotation.</span></span>
19. <span data-ttu-id="6a4d9-142">Haga clic en Enviar presupuesto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-142">Click Send quotation.</span></span>
20. <span data-ttu-id="6a4d9-143">Seleccione Sí en el campo Imprimir presupuesto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-143">Select Yes in the Print quotation field.</span></span>
21. <span data-ttu-id="6a4d9-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6a4d9-144">Click OK.</span></span>
    * <span data-ttu-id="6a4d9-145">El informe puede tardar un minuto en generarse.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-145">The report may take a minute to generate.</span></span> <span data-ttu-id="6a4d9-146">No cierre la página hasta que lo haga.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-146">Don’t close the page until it does so.</span></span>  
22. <span data-ttu-id="6a4d9-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-147">Close the page.</span></span>

## <a name="update-a-sales-quotation"></a><span data-ttu-id="6a4d9-148">Actualizar un presupuesto de ventas</span><span class="sxs-lookup"><span data-stu-id="6a4d9-148">Update a sales quotation</span></span>
1. <span data-ttu-id="6a4d9-149">En el panel de acciones, haga clic en Seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-149">On the Action Pane, click Follow up.</span></span>
2. <span data-ttu-id="6a4d9-150">Haga clic en Convertir en cliente.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-150">Click Convert to customer.</span></span>
3. <span data-ttu-id="6a4d9-151">En el campo Cuenta de cliente, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-151">In the Customer account field, type a value.</span></span>
4. <span data-ttu-id="6a4d9-152">Haga clic en Comprobar.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-152">Click Check.</span></span>
    * <span data-ttu-id="6a4d9-153">Asegúrese de que ve un mensaje que indica que el número de cuenta que ha escrito está libre para usarlo.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-153">Make sure you see a message that the account number you typed in is free to use.</span></span>  
5. <span data-ttu-id="6a4d9-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6a4d9-154">Click OK.</span></span>
    * <span data-ttu-id="6a4d9-155">El sistema ha creado una nueva cuenta de cliente para el cliente potencial en el presupuesto.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-155">The system has now created a new customer account for the prospect on the quotation.</span></span>  
6. <span data-ttu-id="6a4d9-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-156">Close the page.</span></span>
7. <span data-ttu-id="6a4d9-157">En el panel de acciones, haga clic en Seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-157">On the Action Pane, click Follow up.</span></span>
8. <span data-ttu-id="6a4d9-158">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-158">Click Confirm.</span></span>
9. <span data-ttu-id="6a4d9-159">En el campo Motivo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-159">In the Reason field, enter or select a value.</span></span>
10. <span data-ttu-id="6a4d9-160">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6a4d9-160">Click OK.</span></span>
11. <span data-ttu-id="6a4d9-161">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-161">On the Action Pane, click General.</span></span>
12. <span data-ttu-id="6a4d9-162">Haga clic en Pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-162">Click Sales orders.</span></span>
13. <span data-ttu-id="6a4d9-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6a4d9-163">Close the page.</span></span>


